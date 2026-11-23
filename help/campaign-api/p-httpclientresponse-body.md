# body

The body of the HTTP response in the form of a MemoryBuffer object.

```text
body
```

## Remarks

The encoding of the response body is accessible via the [codePage](p-httpclientresponse-codepage.md) property. The body of the HTTP response is given in the form of a [MemoryBuffer](c-memorybuffer.md) object. All methods applicable to a [MemoryBuffer](c-memorybuffer.md) are therefore applicable to the body of the HTTP response. Example:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

## Features

**Property of class:** [HttpClientResponse](c-httpclientresponse.md)

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
