# execute

Executes a SQL command.

```text
execute (command [, value1, ... ])
```

## Parameters

**command** SQL command.

**value1, ...** Variables of the command.

## Return value

The number of records updated or inserted if applicable to the command executed, otherwise zero.

## Remarks

The variables are used to substitute for the parameters of the command. The variable type must match the type declared in the command. The types are the following:

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

The following substitute parameters are automatically replaced by a value and do not required an associated variable.

* $(id) Generates an identifier
* $(id:NmsTrackingLogId) Generates an identifier thanks to a specific sequence
* $(curdate) Current date and time

The operator needs 'sql' rights to use this function, otherwise an exception is raised.

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
