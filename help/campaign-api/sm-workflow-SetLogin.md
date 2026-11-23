# SetLogin

Changes the execution account.

```text
SetLogin ( String workflowId, String login )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**login** Login of the operator or empty string if no operator is associated with this workflow.

## Return value(s)

None.

## Remarks

The execution account associated with a workflow makes it possible to force execution rights to a specific operator rather than the operator who started the workflow. The execution account is not propagated when a workflow is duplicated.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
