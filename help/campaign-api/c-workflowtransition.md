# WorkflowTransition (Class)

Represents a workflow transition.

A transition is an opaque object which is recovered using methods such as or and which is used to ebable task transition.

Example:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Features

**Available in:**

* Workflow
