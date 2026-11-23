# GetStatus

Get job processing progress information. Warning: This API does not guarantee to return a list of unique log entries (the caller has to deduplicate them using their ID ).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Parameters

**id** Job identifier

**lastLogId** Identifier of the last log entry returned in the previous call

**maxLogCount** Maximum number of log entries to send

## Return value(s)

**status** Job status

**returnLogs** Log messages

**properties** Properties (progress...)

## Features

**Schema:** [xtk:job](s-xtk-job.md)

**Static:**

Yes
