# addMethod

Declares a function on the service.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Parameters

**name** Name of the method. This is the name exposed in JavaScript and the name of the SOAP method.

**action** SOAP-Action parameter.

**arguments** Declaration of arguments in the form of a table containing a list of strings grouped by pairs. The first string is the name of the argument and the second corresponds to the type: \["name1", "type1", "name2", "type2", ...\]

**responses** Declaration of return values in the form of a table containing a list of strings grouped by pairs: The first string is the name of the argument and the second corresponds to the type: \["name1", "type1", "name2", "type2", ...\]

**requestNodeName** A string of characters which specifies the name of the XML node of the SOAP query instead of the method name.

**responseNodeName** A string of characters which specifies the name of the XML node of the SOAP response instead of the method name followed by Response.

## Return value

None.

## Remarks

The following types are supported:

* string
* boolean
* long
* short
* byte
* float
* double
* date
* time
* datetime
* NLDocument
* NLElement
* NLRawXML
* NLCollection

When a method is declared on the service, this becomes a method of the service and can be invoked directly by calling the method by its name. The NLRawXML type used on an incoming parameter copies the entire XML node to replace the argument. Used as a return type, it contains the entire first child element of the SOAP response. Its use implies that the SOAP reponse only has one child element. The NLCollection type used on an incoming parameter copies all the child elements to replace the argument. This is useful when the incoming argument is a variable parameter. Used as a return type, it contains the entire SOAP response, since this is the root of the return value. In case of errors, an exception is raised. If this is a correctly formed SOAP error, then the exception raised has a soapFault property and contains the XML node of the SOAP error. Example:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
```

## Features

**Method of class:** [SoapService](c-SoapService.md)

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
