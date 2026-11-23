# WakeupTask

Forces the advance processing of one or more pending tasks.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**taskIdentifier** The identifier of the task (@taskIdentifier field) or an empty string to force the early processing of all the pending tasks associated with a given activity.

**activityName** The name of the activity to force early processing of all associated tasks or an empty string.

## Return value(s)

None.

## Remarks

If neither taskIdentifier, nor activityName are specified, all pending tasks are taken into account.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
