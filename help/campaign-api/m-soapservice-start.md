# start

Launches a query in asynchronous mode.

```text
start (context, name, ...)
```

## Parameters

**context** Any user parameter that will be forwarded to the [complete](p-soapservice-complete.md) function.

**name** Name of the method to call upon.

**...** Function parameters.

## Return value

The created query. This object has no properties or functions, it is useful for the [wait](m-soapservice-wait.md) function that lets you wait until the end of an operation.

## Remarks

The service connection must be asynchronous. If the connection is blocking, an exception is raised. Queries cannot be run if another query is currently being executed on the connection. In this case, an exception is raised.

## Features

**Method of class:** [SoapService](c-soapservice.md)

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
