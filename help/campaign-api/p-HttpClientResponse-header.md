# header

An object which contains all the HTTP headers.

```text
header
```

## Remarks

The name of the properties isn't case-sensitive. Example:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

To recover several headers with the same name, use the [headers](p-HttpClientResponse-headers.md) property rather than the header property.

## Features

**Property of class:** [HttpClientResponse](c-HttpClientResponse.md)

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
