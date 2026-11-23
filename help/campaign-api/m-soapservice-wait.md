# wait

Waits for the end of a list of asynchronous SOAP queries.

```text
wait (requests)
```

## Parameters

**requests** A table of queries.

## Return value

None.

## Remarks

The function doesn't apply to a service but is a function of the SoapService bin. Example:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Once a query is finished, it is automatically deleted from the list. This means that when the function returns control, the table passed as a parameter will be empty. The list can be modified by the [complete](p-soapservice-complete.md) function: for instance, it is possible to start a new query and add it to the list.

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
