# exec

Alias of the execute command. This function is obsolete, use [execute()](m-dbengine-execute.md)

```text
exec (command [, value1, ... ])
```

## Parameters

**command** SQL command.

**value1, ...** Variables of the command.

## Return value

The number of recordings updated or inserted if this applies to the executed command, if not then zero.

## Features

**Method of class:** [DBEngine](c-dbengine.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
