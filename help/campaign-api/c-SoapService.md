# SoapService (Class)

Enables you to perform SOAP calls on a Web service.

## Blocking calls

The following is a typical example of use: You must first create a connection then a service using this connection then finally declare the SOAP methods for this this service. The SOAP method is exposed in the form of a JavaScript method of the service object.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Non-blocking calls

It is possible to perform non-blocking (asynchronous) calls, i.e. to run a SOAP query to a server and to continue executing the script without waiting for the result. The mains differences with the blocking mode are:

* The connection must be created in asynchronous mode

* Use the

  [start](m-SoapService-start.md)

  function.

* Define a

  [complete](p-SoapService-complete.md)

  function on the service, to be called upon when the response is received.

* The

  [SoapService.wait](m-SoapService-wait.md)

  function is used to wait for the end of processing for a set of queries.

The following example script makes a series of 'GetOption" SOAP calls to an Adobe Campaign server by opening 3 connections simultaneously.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Methods

| Method | Description |
| --- | --- |
| [SoapService](m-SoapService-SoapService.md) | Creates a service to call the functions of a Web service. |
| [addMethod](m-SoapService-addMethod.md) | Declares a function on the service. |
| [dispose](m-SoapService-dispose.md) | Frees the resources used by the object. |
| [start](m-SoapService-start.md) | Launches a query in asynchronous mode. |
| [wait](m-SoapService-wait.md) | Waits for the end of a list of asynchronous SOAP queries. |

## Properties

| Property | Description |
| --- | --- |
| [complete](p-SoapService-complete.md) | Function to call up when an asynchronous query is finished. |
| [header](p-SoapService-header.md) | A character string verbatim copied in the SOAP header. |
| [timeout](p-SoapService-timeout.md) | Maximum wait time in milliseconds in case of an asynchronous query. If this parameter isn't defined, the wait time is 5 minutes. |

## Features

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
