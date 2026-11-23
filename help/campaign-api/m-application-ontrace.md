# onTrace

Adds or deletes a trace message interception function.

```text
onTrace ( [function ])
```

## Parameters

**function** The interception function to be added. If this parameter is left out, the most recently added function is deleted.

## Return value

None.

## Remarks

The function takes and object with the following properties as an argument:

* gravity (String) - The message severity ("error", "warning", "info", "status", "verbose")
* type (String) - The message type ("log", "wdbc", etc.)
* message (String) - The message

The function is protected against re-entrance: it will not intercept trace messages which it created itself. Example:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

file.close()
```

## Features

**Method of class:** [Application](c-application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
