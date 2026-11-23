# onLog

Adds or deletes an interception function for the messages written to the journal

```text
onLog ( [function ])
```

## Parameters

**function** The interception function to be added. If this parameter is left out, the most recently added function is deleted.

## Return value

None.

## Remarks

The most recently added function is called up first. The function takes and object with the following properties as an argument:

* type (Number) - The message type (0=error, 1=warning, 2=information, 3=status, 4=verbose)
* code (Number) - The error code (0 if it isn't an error)
* object (String) - Object linked to the message (unused)
* message (String) - The message

The function must return a boolean. The value true will prevent any following interception functions from receiving the message. The function is protected against re-entrance: it will not intercept messages which it wrote to the journal itself. Example:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## Features

**Method of class:** [Application](c-Application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
