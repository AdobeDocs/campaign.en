# PostEvent

Generates an event from any kind of activity.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**activity** The name of the activity from which the event starts

**transition** The name of the transition to activate. If this name is empty, the event will be issued on the first valid transition (expiry type events are ignored).

**parameters** The parameters of the event in the form of an XML element. The name of the element must be variables. If you do not want to pass a variable, you can use an empty element &lt;variables/&gt; or an empty string "".

**complete** All pending tasks of the specified activity are finished.

## Return value(s)

None.

## Remarks

* The command is executed in asynchronous mode and does not have an immediate effect after the return of the method.
* The target workflow must be started when this method is called. If it is not started, an error is written to the corresponding log file.
* If the target workflow is suspended when the method is called, the command is left in the queue until the workflow is resumed.
* There is no restriction on the activity: it is not necessary for it to have a task in progress or even finished.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
