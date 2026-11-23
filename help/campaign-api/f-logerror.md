# logError

Adds an error message to the log of the workflow instance and suspends execution of the script.

```text
logError (message)
```

## Parameters

**message** The message to add to the log.

## Return value

None.

## Remarks

The task in progress behaves as if an error has occurred: An error is flagged and the workflow is suspended. This function is therefore useful to explicitly raise an error on a workflow and to suspend it.

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
