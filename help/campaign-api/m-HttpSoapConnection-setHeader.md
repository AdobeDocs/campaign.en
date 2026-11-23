# setHeader

Specifies an HTTP header.

```text
setHeader (headerName, headerValue)
```

## Parameters

**headerName** String of characters which is the name of the HTTP header.

**headerValue** String of characters which is the content of the HTTP header.

## Return value

None.

## Remarks

Les en-têtes ainsi spécifiés prévalent sur les en-têtes par défaut lors des appels SOAP. Exemple :

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
```

## Features

**Method of class:** [HttpSoapConnection](c-HttpSoapConnection.md)

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
