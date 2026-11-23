# header

A JavaScript object which contains the Header's HTTP headers.

```text
header
```

## Remarks

All the properties of the header object are acessible in read/write mode and are enumerable. Each owner of the header object is an entry in the HTTP header of the query. Property names aren't case-sensitive (as for HTTP headers). Example:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Features

**Property of class:** [HttpClientRequest](c-httpclientrequest.md)

**Read only:**

Yes

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
