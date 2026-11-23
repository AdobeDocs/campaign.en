# execute

Runs the HTTP query.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Parameters

**hasProxy** Boolean set to true if you need to use a HTTP proxy. By default set to false.

**async** Boolean set to true if the query is asynchronous. By default set to false.

**reuseaddr** Boolean set to true if the underlying socket should allow reuse of local addresses. By default set to false.

**context** The context is any object that will be forwarded to the second argument of the [complete](p-httpclientrequest-complete.md) function in case of an asynchronous query.By default set to null.

**timeout** Maximum wait time in milliseconds in case of asynchronous query. If this parameter isn't defined, the wait time is 5 minutes.

## Return value

None.

## Remarks

If the HTTP connection fails, an exception is raised. The [response](p-httpclientrequest-response.md) property only becomes valid after a successful call to the execute function. Example:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

## Features

**Method of class:** [HttpClientRequest](c-httpclientrequest.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
