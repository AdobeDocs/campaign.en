---
product: Adobe Campaign
title: Data model best practices
description: Learn Campaign data model extension best practices
---
# Data model best practices{#data-model-best-practices}

This document outlines key recommendations while designing your Adobe Campaign data model.

Adobe Campaign system is very flexible and can be extended beyond the initial implementation. However, while possibilities are infinite, it is critical to make wise decisions and build strong foundations to start designing your data model.

For a better understanding of Campaign built-in tables and how they relate to each other, refer to [this section](datamodel.md) .

[!DNL :bulb:] Read out [this section](schemas.md) to get started with Campaign schemas. 

[!DNL :bulb:] Learn how to configure extension schemas in order to extend the conceptual data model of the Adobe Campaign database in [this page](extend-schema.md).

## Data model architecture {#data-model-architecture}

Adobe Campaign is a powerful cross-channel campaign management system that can help you align your online and offline strategies to create personalized customer experiences.

### Customer-centric approach {#customer-centric-approach}

While most email service providers are communicating to customers via a list-centric approach, Adobe Campaign relies on a relational database in order to leverage a broader view of the customers and their attributes.

To access the description of each table, go to **[!UICONTROL Admin > Configuration > Data schemas]**, select a resource from the list and click the **[!UICONTROL Documentation]** tab.


>[!NOTE]
>
>Adobe Campaign allows to build a [custom recipient table](custom-recipient.md). However, in most cases, it is recommended to leverage the built-in [Recipient table](datamodel.md#ootb-profiles) which already has pre-built additional tables and features.

### Data for Adobe Campaign {#data-for-campaign}

What data should be sent to Adobe Campaign? It is critical to determine the data required for your marketing activities.

>[!NOTE]
>
>Adobe Campaign is neither a data warehouse nor a reporting tool. Therefore, do not try to import all possible customers and their associated information into Adobe Campaign, or import data which will only be used to build reports.

To make the decision whether an attribute would be needed or not in Adobe Campaign, ask yourself if it would fall under one of these categories:

* Attribute used for **segmentation**
* Attribute used for **data management processes** (aggregate calculation for example)
* Attribute used for **personalization**

If not falling into any of these, you are most likely not going to need this attribute in Adobe Campaign.

### Choice of data types {#data-types}

To ensure good architecture and performance of your system, follow the best practices below to set up data in Adobe Campaign.

* Within large tabl, you could insert string or numeric fields and add links to reference tables (when working with list of values).
* The **expr** attribute  allows to define a schema attribute as a calculated field rather than a physical set value in a table. This can enable access to the information in a different format (as for age and birth date for example) without the need to store both values. This is a good way to avoid duplicating fields. For instance, the Recipient table uses an expression for the domain, which is already present in the email field.
* However, when the expression calculation is complex, it is not recommended to use the **expr** attribute as on-the-fly calculation may impact the performance of your queries.
* The **XML** type is a good way to avoid creating too many fields. But it also takes up disk space as it uses a CLOB column in the database. It also can lead to complex SQL queries and may impact performance.
* The length for a **string** field should always be defined with the column. By default, the maximum length in Adobe Campaign is 16K, but Adobe recommends keeping the field shorter if you already know that the size will not exceed a shorter length.
* It is acceptable to have a field shorter in Adobe Campaign than it is in the source system if you are certain that the size in the source system was overestimated and would not be reached. This could mean a shorter string or smaller integer in Adobe Campaign.

### Choice of fields {#choice-of-fields}

A field is required to be stored in a table if it has a targeting or personalization purpose. In other words, if a field is not used to send a personalized email or used as a criterion in a query, it will unnecessarily take up disk space. 

### Choice of keys {#choice-of-keys}

In addition to the **autouuid** and **autopk** defined by default in most tables, you should consider adding some logical or business keys (account number, client number, and so on). It can be used later for imports/reconciliation or data packages. For more on this, see [Identifiers](#identifiers).

Efficient keys are essential for performance. With Snowflake, you can insert nnumeric or string-based data types as keys for tables.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Identifiers {#identifiers}

Adobe Campaign resources have three identifiers, and it is possible to add an additional identifier.

The following table describe these identifiers and their purpose.

| Identifier | Description | Best practices |
|--- |--- |--- |
| Id | <ul><li>The id is the physical primary key of an Adobe Campaign table. For built-in tables, it is a Universally Unique ID (UUID)</li><li>This identifier must be unique. </li><li>An UUID can be visible in a schema definition.</li></ul> | <ul><li>Auto-generated identifiers should not be used as a reference in a workflow or in a package definition.</li><li>The id in a table is a UUID and this type should not be changed.</li></ul> |
| Name (or internal name) | <ul><li>This information is a unique identifier of a record in a table. This value can be manually updated, usually with a generated name.</li><li>This identifier keeps its value when deployed in a different instance of Adobe Campaign and it should not be empty.</li></ul> | <ul><li>Rename the record name generated by Adobe Campaign if the object is meant to be deploy from an environment to another.</li><li>When an object has a namespace attribute (*schema* for example), this common namespace will be leveraged across all custom objects created. Some reserved namespaces should not be used: *nms*, *xtk*, etc.  Note that some namespaces are internal only. [Learn more](schemas.md#reserved-namespaces).</li><li>When an object does not have any namespace (*workflow* or *delivery* for example), this namespace notion would be added as a prefix of an internal name object: *namespaceMyObjectName*.</li><li>Do not use special characters such as space “ “, semi-column “:” or hyphen “-“. All these characters would be replaced by an underscore “_” (allowed character). For example, “abc-def” and “abc:def” would be stored as “abc_def” and overwrite each other.</li></ul> |
| Label | <ul><li>The label is the business identifier of an object or record in Adobe Campaign.</li><li>This object allows spaces and special characters.</li><li>It does not guarantee the uniqueness of a record.</li></ul>| <ul><li>It is recommended to determine a structure for your object labels.</li><li>This is the most user-friendly solution to identify a record or object for an Adobe Campaign user.</li></ul> |

Adobe Campaign primary key is an auto-generated UUID for all built-in tables. A UUID can also be used for custom tables.

Even if the number of IDs is infinite, you should take care of the size of your database to ensure optimal performances. To prevent any issue, make sure to adjust your instance purge settings. For more on this, see [this section](#data-retention).


## Custom internal keys {#custom-internal-keys}

Primary keys are required for every table created in Adobe Campaign.

Most organizations are importing records from external systems. While the physical key of the Recipient table is the "id" attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When creating a custom table, you have two options:
* A combination of auto-generated key (id) and internal key (custom). This option is interesting if your system key is a composite key or not an integer. With Snowflake, integers or string-based keys will provide higher performances in big tables and joining with other tables.
* Using the primary key as the external system primary key. This solution is usually preferred as it simplifies the approach to import and export data, with a consistent key between different systems. **Autouuid** should be disabled if the key is named “id” and expected to be filled with external values (not auto-generated).

>[!CAUTION]
>
>An autouuid should not be used as a reference in workflows.


## Links and cardinality {#links-and-cardinality}

### Links {#links}

Beware of the "own" integrity on large tables. Deleting records that have large tables in "own" integrity can potentially stop the instance. The table is locked, and the deletions are made one by one. So it's best to use "neutral" integrity on child tables that have large volumes.

Declaring a link as an external join is not good for performance. The zero-id record emulates the external join functionality. It is not necessary to declare external joins if the link uses the **autouuid**.

While it is possible to join any table in a workflow, Adobe recommends defining common links between resources directly in the data structure definition.

Link should be defined in alignment with the actual data in your tables. A wrong definition could impact data retrieved via links, for example unexpectedly duplicating records.

Name your link consistently with the table name: the link name should help understand what the distant table is.

Do not name a link with “id” as a suffix. For example, name it “transaction” rather than “transactionId”.

By default, Adobe Campaign will create a link using the primary key of the external table. For more clarity, it is preferable to explicitly define the join in the link definition.

### Cardinality {#cardinality}

When you design a link, make sure that the target record is unique when a 1-1 relationship has been declared. Otherwise the join may return multiple records when only one is expected. This results in errors during delivery preparation when "the query returns more rows than expected". Set the link name to the same name as the target schema.

Define a link with a cardinality (1-N) in the schema on the (1) side. For example, the relation Recipient (1) – (N) Transaction should be defined in the transaction schema.

Note that a reverse cardinality of a link is (N) by default. It is possible to define a link (1-1) by adding the attribute revCardinality='single' to the link definition.

If the reverse link should not be visible to the user, you can hide it with the link definition revLink='_NONE_'. A good use case for this is to define a link from recipient to the last transaction completed for example. You only need to see the link from recipient to the last transaction and no reverse link is required to be visible from the transaction table.

Links performing an external join (1-0..1) should be used with care as it will impact the system performance.

## Data retention {#data-retention}

Adobe Campaign is neither a data warehouse nor a reporting tool. Therefore, to ensure good performance of the Adobe Campaign solution, database growth should stay under control. To achieve this, following some of the best practices below may help.

Regarding retention, built-in log tables in Campaign have pre-set retention periods on them, generally limiting their data storage to six months or less.

The following are the default retention values for built-in tables. Be aware that the retention configuration is set by Adobe technical administrators during implementation and values may vary for each implementation, based on customer requirements.

* **Consolidated tracking**: 1 year
* **Delivery logs**: 6 months
* **Tracking logs**: 1 year
* **Deleted deliveries**: 1 week
* **Import rejects**: 6 months
* **Visitor profiles**: 1 month
* **Offer propositions**: 1 year
* **Events**: 1 month
* **Statistics of event processing**: 1 year
* **Archived events**: 1 year
* **Pipeline events ignored**: 1 month

>[!CAUTION]
>
>Custom tables are not purged with the standard cleanup process. While this might not be required on day one, do not forget to build a purge process for your custom tables as this could lead to performance challenges.

There are a few solutions to minimize the need of records in Adobe Campaign:
* Export the data in a data warehouse outside of Adobe Campaign.
* Generate aggregated values that will use less space while being sufficient for your marketing practices. For example, you do not need the full customer transaction history in Adobe Campaign to keep track of the last purchases.

You can declare the "deleteStatus" attribute in a schema. It is more efficient to mark the record as deleted, then postpone the deletion in the cleanup task.

[!DNL :speech_balloon:] As a Managed Cloud Services user, reach out to the Adobe consultants or technical administrators to learn more about retention or if you need to set retention for custom tables.

## Performance {#performance}

In order to ensure better performance at any time, follow the best practices below.

### General recommendations {#general-recommendations}

* Avoid using operations like “CONTAINS” in queries. If you know what is expected and want to be filtered for, apply the same condition with an “EQUAL TO” or other specific filter operators.
* Try and make sure the processes like import and export happen off business hours.
* Make sure there is a schedule for all the daily activities and stick to the schedule.
* If one or few of the daily processes fail and if it is mandatory to run it on that same day, make sure there are no conflicting processes running when the manual process is kicked off as this could affect the system performance.
* Make sure none of the daily campaign is run during the import process or when any manual process is executed.
* Use one or several reference tables rather than duplicating a field in every row. When using key/value pairs, it is preferred to choose a numerical key.
* A short string remains acceptable. In case references tables are already in place in an external system, reusing the same will facilitate the data integration with Adobe Campaign.

### One-to-many relationships {#one-to-many-relationships}

* Data design impacts usability and functionality. If you design your data model with lots of one-to-many relationships, it makes it more difficult for users to construct meaningful logic in the application. One-to-many filter logic can be difficult for non-technical marketers to correctly construct and understand.
* It is good to have all the essential fields in one table because it makes it easier for users to build queries. Sometimes it is also good for performance to duplicate some fields across tables if it can avoid a join. 
* Certain built-in functionalities will not be able to reference one-to-many relationships, for example, Offer Weighting formula and Deliveries.

## Large tables {#large-tables}

Adobe Campaign relies on third-party database engines. Depending on the provider, optimizing performance for larger tables may require a specific design.

Below are a few common best practices that should be followed when designing your data model using large tables and complex joins.

* When using additional custom recipient tables, make sure you have a dedicated log table for each delivery mapping.
* Reduce the number of columns, particularly by identifying those that are unused.
* Optimize the data model relations by avoiding complex joins, such as joins on several conditions and/or several columns.
* For join keys, you can use numeric or string-based values.
* Reduce as much as you can the depth of log retention. If your need deeper history, you can aggregate computation and/or handle custom log tables to store larger history.

### Size of tables {#size-of-tables}

The table size is a combination of the number of records and the number of columns per record. Both can impact the performance of queries.

* A **small-size** table is similar to the Delivery table. 
* A **medium size** table is the same as the size of the Recipient table. It has one record per customer.
* A **large-size** table is similar to the Broad log table. It has many records per customer.
For example, if your database contains 10 million recipients, the Broad log table contains about 100 to 200 million messages, and the Delivery table contains a few thousand records.

The number of rows impacts performance as well. The Adobe Campaign database is not designed to store historical data that are not actively used for targeting or personalization purpose - this is an operational database.

To prevent any performance issue related to the high number of rows, only keep the necessary records in the database. Any other record should be exported to a third-party data warehouse and removed from the Adobe Campaign operational database.

Here are a few best practices regarding the size of tables:

* Design large tables with fewer fields and more numeric data.
* Do not use large number type of column to store small numbers like boolean values.
* Remove unsused columns from the table definition.
* Do not keep historical or inactive data in your Adobe Campaign database (export and cleanup).
