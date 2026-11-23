# wait

Waits until the end of a list of asynchronous queries.

```text
wait (requests,waitAll)
```

## Parameters

**requests** A table of queries.

**waitAll** Boolean (by default true), wait all requests from the query list to be completed. When set to false, if a least one request is completed, the function gets out of the listening loop.

## Return value

None.

## Remarks

The function doesn't apply to a query but is a function of the HttpClientRequest bin. Example:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

A query may only be added to the list if it is asynchronous and if the [execute](m-HttpClientRequest-execute.md) call hasn't raised an exception. Once a query is finished, it is automatically deleted from the list. This means that when the function returns control, the table passed as a parameter will be empty. The list can be modified by the [complete](p-HttpClientRequest-complete.md) function: for instance, it is possible to start a new query and add it to the list.

## Features

**Method of class:** [HttpClientRequest](c-HttpClientRequest.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
