# CheckPlanningTask

Internal function used to check overloads within the schedules of task operators (returns 'true' in case of overload). This function also checks the consistency of related task schedules and updates them if necessary.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Parameters

**taskId** Task identifier.

## Return value(s)

**workloadAlert** Resource overload warning

## Features

**Schema:** [nms:task](s-nms-task.md)

**Static:**

Yes
