# getConnection

Returns a new connection to the database server.

```text
getConnection ()
```

## Parameters

None.

## Return value

A [connection](c-dbengine.md) to the database server.

## Remarks

It is possible to free the connection before the end of script execution using the [dispose](m-dbengine-dispose.md) method.

## Features

**Method of class:** [Application](c-application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
