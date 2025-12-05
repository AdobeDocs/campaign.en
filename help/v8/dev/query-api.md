---
title: Query the database with queryDef
description: Learn how to use queryDef and NLWS methods to query the Campaign database
feature: API
role: Developer
level: Intermediate, Experienced
hide: yes
hidefromtoc: yes
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
---
# Query the database with queryDef {#query-database-api}

[!DNL Adobe Campaign] provides powerful JavaScript methods to interact with the database using `queryDef` and the `NLWS` object. These SOAP-based methods allow you to load, create, update, and query data using JSON, XML, or SQL.

>[!NOTE]
>
>This documentation covers data-oriented APIs for querying the database programmatically. For REST APIs, refer to [Get started with REST APIs](api/get-started-apis.md). For visual query building, refer to [Work with the query editor](../start/query-editor.md).

## What is NLWS? {#what-is-nlws}

`NLWS` (Neolane Web Services) is the global JavaScript object used to access [!DNL Adobe Campaign]'s SOAP-based API methods. Schemas are properties of the `NLWS` object, allowing you to interact with Campaign entities programmatically.

According to the [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}, "schemas are 'NLWS' global objects." The syntax to access schema methods follows this pattern:

```javascript
NLWS.<namespace><SchemaName>.<method>()
```

**Examples:**

* `NLWS.nmsRecipient` - Access methods for the recipient schema (`nms:recipient`)
* `NLWS.nmsDelivery` - Access methods for the delivery schema (`nms:delivery`)
* `NLWS.xtkQueryDef` - Access queryDef methods for querying the database

Common API methods include:

* `load(id)` - Load an entity by its ID. [Learn more](https://experienceleague.adobe.com/developer/campaign-api/api/f-load.html){target="_blank"}
* `create(data)` - Create a new entity
* `save()` - Save changes to an entity

**Example from official documentation:**

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

>[!NOTE]
>
>**Alternative syntax:** For backward compatibility, you may also see lowercase namespace syntax in some documentation (e.g., `nms.recipient.create()`, `xtk.queryDef.create()`). Both syntaxes work, but `NLWS` is the standard documented in the official Campaign JSAPI reference.

## Prerequisites {#prerequisites}

Before using queryDef and NLWS methods, you should be familiar with:

* JavaScript
* [!DNL Adobe Campaign] data model and schemas
* XPath expressions for navigating schema elements

**Understanding the Campaign data model:**

Adobe Campaign comes with a pre-defined data model consisting of tables linked together in a Cloud database. The basic structure includes:

* **Recipient table** (`nmsRecipient`) - Main table storing marketing profiles
* **Delivery table** (`nmsDelivery`) - Stores delivery actions and templates with parameters for performing deliveries
* **Logs tables** - Store execution logs:
  * `nmsBroadLogRcp` - Delivery logs for all messages sent to recipients
  * `nmsTrackingLogRcp` - Tracking logs for recipient reactions (opens, clicks)
* **Technical tables** - Store system data like operators (`xtkGroup`), sessions (`xtkSessionInfo`), workflows (`xtkWorkflow`)

To access schema descriptions in the Campaign interface, browse to **Administration > Configuration > Data schemas**, select a resource, and click the **Documentation** tab.

## Entity Schema methods {#entity-schema-methods}

Each schema in [!DNL Adobe Campaign] (e.g., `nms:recipient`, `nms:delivery`) comes with methods accessible through the `NLWS` object. These methods provide a convenient way to interact with database entities.

### Static methods {#static-methods}

Static SOAP methods are accessed by invoking a method on the object representing the schema. For example, `NLWS.xtkWorkflow.PostEvent()` invokes a static method.

### Non-static methods {#non-static-methods}

To use non-static SOAP methods, you must first retrieve an entity using the `load` or `create` methods on the corresponding schemas. Learn more in the [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-14.html){target="_blank"}.

### Load, save, and create entities {#load-save-create}

**Load an entity by ID and update it:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Create a recipient using JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Create a recipient using XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## QueryDef overview {#querydef-overview}

The `xtk:queryDef` schema provides methods to build and execute database queries. You can use `NLWS.xtkQueryDef.create()` to build queries with JSON or XML syntax.

**Available operations:**

* `select` - Retrieve multiple records
* `get` - Retrieve a single record (SQL `LIMIT 1`)
* `getIfExists` - Retrieve a single record, return null if not found
* `count` - Count records matching criteria

Learn more about queryDef methods in the [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}.

## Query with JSON {#query-json}

Use `NLWS.xtkQueryDef.create()` to build queries with JSON syntax. The `get` operation retrieves a single record (SQL `LIMIT 1`), while `select` retrieves multiple records.

**Get a single recipient:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Use `getIfExists` to avoid exceptions:**

If the record might not exist, use `operation: "getIfExists"` instead of `get` to avoid exceptions:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Select multiple records {#select-multiple}

Use the `select` operation to retrieve multiple records. You can add conditions, ordering, and limits.

**Query workflows with filters and ordering:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Query deliveries with XML syntax:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>**Result limits:** Campaign automatically limits query results to prevent memory issues:
>* Default limit varies by context (typically 200-10,000 records)
>* Use `lineCount` to explicitly set the maximum number of results
>* For large datasets (>1000 records), use workflows instead of queryDef. Workflows are designed to process millions of rows efficiently.

Learn more about [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html){target="_blank"} and [query best practices](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}.

## Query workflow transition data {#workflow-transition-data}

When working with JavaScript activities in workflows, you can query data from incoming transitions using `vars.targetSchema` and `vars.tableName`.

**Query recipient data from a workflow transition:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Always use parameterized queries with `$(sz)` for strings and `$(l)` for integers to prevent SQL injection vulnerabilities. Learn more in the [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}.

## Count records {#count-records}

Use `Count(@id)` with an alias to count records.

**Count running hypotheses:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Count with multiple conditions:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Distribution of values {#distribution-values}

Get the distribution of values for a specific field, useful for analyzing data patterns.

**Distribution of country codes:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Query enumerations with analyze {#analyze-enumerations}

The `analyze` option returns user-friendly names for enumeration values. Instead of just numeric values, Campaign will also return the string value and label using "Name" and "Label" suffixes.

**Query delivery mapping with enumeration analysis:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:deliveryMapping",
    operation: "get",
    select: {
      node: [
        {expr: "@id"},
        {expr: "@name"},
        {expr: "[storage/@exclusionType]", analyze: true}  // Analyze enumeration
      ]
    },
    where: {
      condition: [{expr: "@name='mapRecipient'"}]
    }
  }
});

var mapping = query.ExecuteQuery();

// Result includes:
// - exclusionType: 2 (numeric value)
// - exclusionTypeName: "excludeRecipient" (string value)
// - exclusionTypeLabel: "Exclude recipient" (display label)
logInfo("Type: " + mapping.$exclusionType);
logInfo("Name: " + mapping.$exclusionTypeName);
logInfo("Label: " + mapping.$exclusionTypeLabel);
```

Learn more about the [analyze option](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#the-analyze-option){target="_blank"}.

## Pagination {#pagination}

Use `lineCount` and `startLine` to paginate through large result sets.

**Retrieve records in pages:**

```javascript
// Get records 3 and 4 (skip first 2)
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    lineCount: 2,     // Number of records per page
    startLine: 2,     // Starting position (0-indexed)
    select: {
      node: [
        {expr: "@id"},
        {expr: "@email"}
      ]
    },
    orderBy: {
      node: [{expr: "@id"}]  // Critical: Always use orderBy for pagination
    }
  }
});

var recipients = query.ExecuteQuery();
```

>[!CAUTION]
>
>**Pagination requires orderBy:** Without an `orderBy` clause, query results are not guaranteed to be in a consistent order. Subsequent calls may return different pages or duplicate records. Always include an `orderBy` when using pagination.

Learn more about [pagination](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html#pagination){target="_blank"}.

## Dynamic query construction {#dynamic-queries}

Build queries dynamically by appending conditions programmatically.

**Append conditions to an existing query:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Build select and where clauses in loops:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Advanced queryDef methods {#advanced-methods}

Beyond `ExecuteQuery()`, queryDef provides several specialized methods for advanced use cases.

### BuildQuery - Generate SQL without executing {#build-query}

Use `BuildQuery()` to generate the SQL statement without executing it. This is useful for debugging, logging, or passing queries to external systems.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Learn more about [BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}.

### BuildQueryEx - Get SQL with format string {#build-query-ex}

`BuildQueryEx()` returns both the SQL query and a format string compatible with the `sqlSelect()` function.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Learn more about [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}.

### SelectAll - Add all fields to select {#select-all}

The `SelectAll()` method automatically adds all fields from the schema to the select clause, saving you from listing each field manually.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Learn more about [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}.

### Update - Mass update records {#mass-update}

The `Update()` method allows you to perform mass updates on records matching your query criteria without loading each record individually.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>Mass updates affect all records matching the where clause. Always test your where conditions with a select query first to verify which records will be affected.

Learn more about [Update](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}.

### GetInstanceFromModel - Query template instances {#get-instance-from-model}

Use `GetInstanceFromModel()` to retrieve data from instances created from templates.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Learn more about [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}.

## Batch operations {#batch-operations}

Process multiple records in batch to improve performance.

**Batch update delivery labels:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Raw SQL execution {#raw-sql}

For complex operations, you can execute raw SQL directly.

**Execute parameterized SQL:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Query with sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>When using raw SQL:
>
>* Always validate and sanitize user inputs
>* Use parameterized queries with `$(sz)`, `$(l)`, `$(dt)` etc.
>* Be aware of the differences between the local and cloud databases in [FFDA deployments](../architecture/enterprise-deployment.md)

## Best practices {#best-practices}

When working with queryDef and NLWS methods:

* **Use workflows for large datasets** - QueryDef is not designed for high-volume data processing. For datasets with more than 1,000 records, use workflows which can handle millions of rows efficiently. Learn more in the [Campaign SDK documentation](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* **Use parameterized queries** - Always use bound parameters (`$(sz)`, `$(l)`) with `sqlExec` to prevent SQL injection
* **Set explicit limits** - Use `lineCount` to control result size. Campaign's default limits vary by context (200-10,000 records)
* **Use orderBy with pagination** - Always include an `orderBy` clause when using `startLine` and `lineCount` to ensure consistent pagination
* **Use getIfExists** - Use `operation: "getIfExists"` when records might not exist to avoid exceptions
* **Use analyze for enumerations** - Add `analyze: true` to select nodes to get user-friendly enumeration names and labels
* **Optimize queries** - Add appropriate `where` conditions to limit result sets
* **Batch processing** - Process multiple records in batches to avoid memory issues and timeouts
* **FFDA awareness** - In [Enterprise (FFDA) deployments](../architecture/enterprise-deployment.md), be aware that [!DNL Campaign] works with two databases



## Practical use cases {#use-cases}

### Debug and log queries {#debug-queries}

Use `BuildQuery()` to inspect the generated SQL before execution:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Duplicate a record with SelectAll {#duplicate-record}

Use `SelectAll()` to copy all fields when duplicating records:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Validate before mass update {#validate-mass-update}

Always preview affected records before performing mass updates:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Query definition syntax reference {#querydef-reference}

Complete structure of the `queryDef` object:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Related topics {#related-topics}

* [Get started with Campaign APIs](api.md)
* [Campaign JavaScript SDK - Query API](https://opensource.adobe.com/acc-js-sdk/xtkQueryDef.html){target="_blank"}
* [queryDef API Reference](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
* [Work with schemas](schemas.md)
* [Work with the query editor](../start/query-editor.md)

