# setNextProcessingDate

Forces the next date of processing by the task.

```text
setNextProcessingDate (timestamp)
```

## Parameters

**timestamp** Next processing date. If empty, the next processing will be straightaway.

## Return value

None.

## Remarks

* Using this method overrides the next processing date if given by the scheduler.
* The next processing is always performed by the \*\_recall() function.

## Features

**Method of class:** [WorkflowTask](c-workflowtask.md)

**Available in:**

* Workflow
