# queryWithTypes

Executes a SELECT type SQL query with column type specification.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Parameters

**command** SQL command.

**types** Table containing the column type.

**value1, ...** Command variables.

## Return value

A cursor that enables you to iterate on the query result.

## Remarks

Warning: contrary to what is stated in the Features section, the queryWithTypes function is not available in WebApp. The function is identical to [query](m-DBEngine-query.md), with the added columns type. In most cases, column type isn't used as it can be inferred automatically. This is why the [query](m-DBEngine-query.md) should be preferred. However in some cases, specially with Oracle and date type columns, it can be necessary to explicit the type. Column types are character strings in the following list:

* string
* datetime
* date
* time
* timespan
* double
* float
* boolean
* byte
* short
* long
* int64
* memo
* blob
* link
* bin

Example:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

The operator must have 'sql' rights to use this function, otherwise an exception is raised.

## Features

**Method of class:** [DBEngine](c-DBEngine.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
