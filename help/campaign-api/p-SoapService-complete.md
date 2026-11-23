# complete

Function to call up when an asynchronous query is finished.

```text
complete
```

## Remarks

The function must accept four arguments:

* The service
* The result
* The context: this is the parameter passed to the [start](m-SoapService-start.md) function
* The status

The status can have the following values:

* "success" means that a result was received.
* "error" can mean that the communication was interrupted, that the response was badly structured or that an HTTP error occurred.
* "fault" if a SOAP error is returned. In this case, the result contains an object describing the error.
* "timeout" means that the connection could not be established or that no response was received within the configured deadline.

When the result is "success", the result depends on the number of parameters returned:

* void if the query doesn't return any values
* The value if the query returns a single parameter
* a table if the query returns several parameters

When the status is "fault", the result is an object which contains the following properties:

* message: the error description message.
* object: an XML object containing the detail of the error.

Example:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
```

## Features

**Property of class:** [SoapService](c-SoapService.md)

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
