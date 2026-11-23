# sqlExec

Executes an SQL script.

```text
sqlExec (query [, value1, ... ])
```

## Parameters

**query** The SQL query.

**value1, ...** Variables of the SQL query.

## Return value

The number of records updated or inserted in case of an UPDATE ou INSERT SQL command.

## Remarks

Variables replace the parameters in the command. The variable type must coincide with the parameter declared in the command. These variables are available in a 'select' or 'update' type declaration. We have the following types:

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
* $(dur) timespan en millisecondes (ms)

The following substitution parameters (only valid for an "update") are automatically replaced with a value and don't need a linked variable.

* $(id) generate an identifier
* $(id:NmsTrackingLogId) generate an identifier by using a specific sequence
* $(curdate) current date and hour

The operator must have the 'sql' right to use this function, otherwise an exception is raised. Example:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
```

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
