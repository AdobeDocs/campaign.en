# job

Batch jobs executed on the application server

## Methods

| Method | Description |
| --- | --- |
| [Cancel](sm-job-Cancel.md) | Cancel a job |
| [CheckIfJobInProcess](sm-job-CheckIfJobInProcess.md) | Check if the job is still running |
| [Execute](sm-job-Execute.md) | Executes a job synchronously (in this mode, progress information and cancelation are not available). |
| [FilesExist](sm-job-FilesExist.md) | Checks if files already exist on server (as files or in the resource table). |
| [GetJobsInProcess](sm-job-GetJobsInProcess.md) | Returns the non-external jobs currently running |
| [GetStatus](sm-job-GetStatus.md) | Get job processing progress information. Warning: This API does not guarantee to return a list of unique log entries (the caller has to deduplicate them using their ID ). |
| [HasWarning](sm-job-HasWarning.md) | Queries if warnings or errors have been generated for this job |
| [Pause](sm-job-Pause.md) | Pause a job |
| [Submit](sm-job-Submit.md) | Submits a job for an asynchronous processing |
| [SubmitFromModel](sm-job-SubmitFromModel.md) | Submits a job from a template |
| [SubmitSoapCall](sm-job-SubmitSoapCall.md) | Submits a job for an asynchronous processing |
| [WaitJobCancelled](sm-job-WaitJobCancelled.md) | Waiting for the job to be canceled |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
