# query

Executes a SELECT type SQL query.

```text
query (command [, value1, ... ])
```

## Parameters

**command** SQL command.

**value1, ...** Variables of the command.

## Return value

A cursor which enables you to iterate on the query result.

## Remarks

Warning: contrary to what is stated in the Features section, the query function is not available in WebApp. Variables replace the parameters of the command. The variable type must match the parameter declared in the command. The following types are available:

* $(sz) string
* $(m) memo
* $(l) long
* $(s) short
* $(b) byte
* $(d) double
* $(f) float
* $(ts) timestamp
* $(dt) date
* $(tm) time
* $(dur) timespan

The following substitution parameters are automatically replaced with a value and do not need a linked variable.

* $(id) Generates an identifier
* $(id:NmsTrackingLogId) Generates an identifier thanks to a specific sequence
* $(curdate) Current date and time

Iteration on the cursor takes place via a "for each" and returns a table for each recovered line. Each element of the table matches a field of the query and the type of element depends on the type of field. Example:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

In this example, row\[0\] is a number which coincides with iOperatorId, row\[1\] is a string of characters which coincides with sName and row\[2\] is a date which coincides with tsLastModified. The operator needs 'sql' rights to use this function, otherwise an exception is raised.

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
