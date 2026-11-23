# GetLogin

Returns information from the execution account.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

## Return value(s)

**id** Identifier of the operator or 0 if no operator is associated with this workflow.

**login** Login of the operator or empty string if no operator is associated with this workflow.

**cs** Description string of the operator or empty string if no operator is associated with this workflow.

## Remarks

The execution account associated with a workflow makes it possible to force execution rights to a specific operator rather than the operator who started the workflow. The execution account is not propagated when a workflow is duplicated.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
