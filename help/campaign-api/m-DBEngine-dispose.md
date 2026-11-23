# dispose

Frees the connection from all resources linked to it.

```text
dispose ()
```

## Parameters

None.

## Return value

None.

## Remarks

A connection created using the [application.getConnection()](m-Application-getConnection.md) method is freed automatically at the end of the script. Calling this method is useful for scripts which can have a long life-span.

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
