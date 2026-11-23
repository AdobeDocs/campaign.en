# HttpClientRequest (Class)

An HttpClientRequest object lets you perform certain operations as an HTTP client.

Exemple :

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## "Keep Alive"

The object can be used in two different modes: standard or keep alive. Standard mode lets you send a single query, keep alive mode lets you send several queries while maintaining the connection open. The status of the object depends on the method use sequence. If the connect() method is called, the object switches to "keep alive" mode. Example

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Asynchronous queries

Queries are executed in blocking mode by default, which means that the

[execute](m-HttpClientRequest-execute.md)

function only returns control once the query is sent and the response received. It is also possible to execute queries in asynchronous mode. In this case, the

[execute](m-HttpClientRequest-execute.md)

function returns control immediately, and a function will be called once the response is received. This enables the simultaneous execution of several queries. The following program is a full example that shows you how to run a series of HTTP uploads opening 3 connections at the same time, where each upload starts once the last one is finished.

```text
var list = [ "http://www.adobe.com/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Methods

| Method | Description |
| --- | --- |
| [HttpClientRequest](m-HttpClientRequest-HttpClientRequest.md) | Creates a new object to run an HTTP client query. |
| [connect](m-HttpClientRequest-connect.md) | Opens the HTTP connection and passes the object into "keep-alive" mode |
| [disconnect](m-HttpClientRequest-disconnect.md) | Closes the HTTP connection of an object in "keep-alive" mode. |
| [execute](m-HttpClientRequest-execute.md) | Runs the HTTP query. |
| [wait](m-HttpClientRequest-wait.md) | Watis until the end of a list of asynchronous queries. |

## Properties

| Property | Description |
| --- | --- |
| [body](p-HttpClientRequest-body.md) | The body of the HTTP query. |
| [complete](p-HttpClientRequest-complete.md) | Function to call up when an asynchronous query is finished. |
| [header](p-HttpClientRequest-header.md) | A JavaScript object which contains the Header's HTTP headers. |
| [method](p-HttpClientRequest-method.md) | The HTTP method, in the form of a string of characters |
| [response](p-HttpClientRequest-response.md) | The response of the HTTP query. This is a HttpClientResponse type object |
| [url](p-HttpClientRequest-url.md) | The address of the remote server. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
