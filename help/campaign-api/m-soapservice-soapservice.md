# SoapService

Creates a service to call the functions of a Web service.

```text
SoapService (cnx, namespace)
```

## Parameters

**cnx** The ([HttpSoapConnection](c-httpsoapconnection.md)) HTTP connection.

**namespace** Namespace of the service.

## Return value

None.

## Remarks

Example:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Features

**Method of class:** [SoapService](c-soapservice.md)

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
