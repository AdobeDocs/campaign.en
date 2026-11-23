# header

A character string verbatim copied in the SOAP header.

```text
header
```

## Remarks

Les chaînes de caractères sont recopiées in-extenso dans l'en-tête SOAP sans vérification. Example:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
```

## Features

**Property of class:** [SoapService](c-soapservice.md)

**Read only:**

No

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
