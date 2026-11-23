# sqlGetMemo

Returns the Memo field resulting from an SQL query.

```text
sqlGetMemo (query [, value1, ... ])
```

## Parameters

**query** The SQL query.

**value1, ...** Variables of the SQL query.

## Return value

The Memo field that matches the query.

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
* $(dur) timespan in milliseconds (ms)

The following substitution parameters (only valid for an "update") are automatically replaced with a value and don't need a linked variable.

* $(id) Generates an identifier
* $(id:NmsTrackingLogId) Generates an identifier using a specific sequence
* $(curdate) Current date and time

Using variables does not affect Adobe Campaign performances. The SQL query must select a single line and a single text type field. The operator must have the 'sql' right to use this function, otherwise an exception is raised. Example:

```javascript
      var logData = sqlGetMemo('select log from IncomingLog where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
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
