# Cleanup

Purges workflow history.

```text
Cleanup ( String workflowId )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

## Return value(s)

None.

## Remarks

Deletes all processed events, finished tasks, failed tasks and log messages. Also deletes progress from the diagram if the workflow is finished. This method deletes the data that is no longer used by the workflow engine only and does not impact the behavior of the workflow.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
