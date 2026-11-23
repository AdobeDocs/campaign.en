# forward

Redirects the query towards another page without going via the client.

```text
forward (location)
```

## Parameters

**location** The redirection URL.

## Return value

None.

## Remarks

forward lets you carry out a preliminary process before transferring the query to another resource which will produce the content of the response. No data must have been returned to the client as a reponse before a forward call, otherwise an error will be raised.

## Features

**Method of class:** [HttpServletRequest](c-HttpServletRequest.md)

**Available in:**

* JSSP
* WebApp
