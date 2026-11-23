# complete

Function to call up when an asynchronous query is finished.

```text
complete
```

## Remarks

The function must accept three arguments:

* The query
* The context
* The status: "success", "error" or "timeout"

The "success" status means that a response has been received, but the response can have any code (200, 404, 503, etc.). The "error" status may point to an interruption of the communication of a badly structured response. The "timeout" status means that the connection could not be established, or that no response was received within the configured deadline. Example:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
```

## Features

**Property of class:** [HttpClientRequest](c-HttpClientRequest.md)

**Read only:**

No

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
