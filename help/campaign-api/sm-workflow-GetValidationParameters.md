# GetValidationParameters

Returns the parameters of a workflow task in progress.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**taskIdentifier** The identifier of the approval-type task (@taskIdentifier field).

## Return value(s)

**content** The XML document containing the parameters.

## Remarks

The returned document contains all the information concerning the validation, who responded and who may still respond.

* Thetitle, creationDate, processingDate, timeout, status, abortReason and completionDate attributes correspond to the attributes in the validation task.
* isAssignee: the current operator is in the group assigned to this task.
* hasResponded: the current operator has already responded.
* canReply: the current operator can respond (either nobody has responded yet, or multiple responses are authorized.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
