# SubmitFromModel

Submits a job from a template

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Parameters

**schema** Job template schema

**where** Template selection expression

**methodName** Name of the method to call

**diff** XML content to add to the template

**async** Perform an asynchronous job submission

## Return value(s)

**jobId** Identifier of job just created

## Features

**Schema:** [xtk:job](s-xtk-job.md)

**Static:**

Yes
