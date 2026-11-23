# Execute

Executes a job synchronously (in this mode, progress information and cancelation are not available).

```text
String id = job.Execute ( String methodName ) const
```

## Parameters

**methodName** Name of the method to call on entity

## Return value(s)

**id** Identifier of the job created (returned even of the job has failed if created in the database)

## Features

**Schema:** [xtk:job](s-xtk-job.md)

**Static:**

No

**Const:**

Yes

**Key only:**

No
