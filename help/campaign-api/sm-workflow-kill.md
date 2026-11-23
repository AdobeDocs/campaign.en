# Kill

Unconditionally stops a workflow.

```text
Kill ( String workflowId )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

## Return value(s)

None.

## Remarks

This method is useful if a workflow cannot be stopped normally. This can happen if the workflow or a task have a affinity in particular or if the wfserver module handling this affinity if no longer running. In this case, the workflow remains flagged 'Stop requested' and may only be stopped by the Kill command.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
