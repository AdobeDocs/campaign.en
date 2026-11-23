# HttpClientRequest

Creates a new object to run an HTTP client query.

```text
HttpClientRequest ( [URL ])
```

## Parameters

**URL** URL of the query's recipient.

## Return value

None.

## Remarks

If the FTP command fails, an exception is raised. Example:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

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
