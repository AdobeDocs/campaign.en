# connect

Opens the HTTP connection and passes the object into "keep-alive" mode

```text
connect ( [hasProxy ] [, async ])
```

## Parameters

**hasProxy** Boolean to true if you need to use a proxy HTTP. By default set to false.

**async** Boolean set to true if the connection is destined to execute an asynchronous query. Set to false by default.

## Return value

None.

## Remarks

If the HTTP connection fails, an exception is raised. The response property only becomes valid after a successful call to the execute function. Don't forget to call disconnect() once you've finished using the connection. Example:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
