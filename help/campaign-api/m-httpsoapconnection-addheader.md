# addHeader

Adds an HTTP header

```text
addHeader (headerName, headerValue)
```

## Parameters

**headerName** String of characters which is the name of the HTTP header.

**headerValue** String of characters which is the content of the HTTP header.

## Return value

None.

## Remarks

The headers specified this way prevail over default headers during SOAP calls. Example:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.addHeader("Authorization","Basic " + memBuf.toBase64());
```

## Features

**Method of class:** [HttpSoapConnection](c-httpsoapconnection.md)

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
