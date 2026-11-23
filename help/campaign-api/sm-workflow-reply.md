# Reply

Responds to a validation-type task in progress.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**taskIdentifier** The identifier of the approval-type task (@taskIdentifier field).

**response** The comment associated with the response.

**choice** The choice of the response. This choice must match the name of the transition to activate.

## Return value(s)

None.

## Remarks

The current operator must be in the group assigned to the task.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
