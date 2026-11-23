# getDBMSType

Returns the server type of the database.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Parameters

**name** Name of the data source.

**checkIfUpdated** Check that the schema has been updated in the cache. No impact if the schema is already instanciated in the script.

## Return value

A text string containing the type of server of the database.

## Remarks

If the data source isn't specified, the function uses 'nms:default' by default. The data source must exist, otherwise an exception is raised.

## Features

**Method of class:** [Application](c-Application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
