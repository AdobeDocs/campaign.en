# HttpSoapConnection

Creates an HTTP connection to a SOAP server.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Parameters

**url** URL of the server including the path.

**codepage** The encoding for the serialization of the SOAP call. This optional paramter allows you to specify the character encoding. By default, the encoding is UTF-8. Example:

* iso-8859-1
* utf-8
* utf-16

**protocol** The type of SOAP protocol used. This optional parameter lets you specify the SOAP protocol used, which is SOAP\_11 by default Possible values:

* SOAP\_11: SOAP protocol 1.1.
* SOAP\_12: SOAP protocol 1.2.
* 0: SOAP protocol internal to Adobe Campaign.

**async** Boolean set to true if the connection is destined to execute an asynchronous query. Set to false by default.

## Return value

None.

## Remarks

Examples:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
