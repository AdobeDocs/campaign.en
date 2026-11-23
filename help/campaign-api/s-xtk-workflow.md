# workflow

Workflows definitions

## Methods

| Method | Description |
| --- | --- |
| [Cleanup](sm-workflow-Cleanup.md) | Purges workflow history. |
| [DeleteResult](sm-workflow-DeleteResult.md) | Erases the results of one or more activities. |
| [Execute](sm-workflow-Execute.md) | Executes a workflow immediately and waits for it to finish. |
| [ExecuteInstance](sm-workflow-ExecuteInstance.md) | Executes a workflow immediately and waits for it to finish. |
| [GetLogin](sm-workflow-GetLogin.md) | Returns information from the execution account. |
| [GetValidationParameters](sm-workflow-GetValidationParameters.md) | Returns the parameters of a workflow task in progress. |
| [Kill](sm-workflow-Kill.md) | Unconditionally stops a workflow. |
| [Pause](sm-workflow-Pause.md) | Suspends execution of a workflow in progress. |
| [PostEvent](sm-workflow-PostEvent.md) | Generates an event from any kind of activity. |
| [Reply](sm-workflow-Reply.md) | Responds to a validation-type task in progress. |
| [Restart](sm-workflow-Restart.md) | Links together a workflow stop and a workflow start. |
| [RestartTask](sm-workflow-RestartTask.md) | Forces restarting of one or more finished tasks. |
| [SetLogin](sm-workflow-SetLogin.md) | Changes the execution account. |
| [Simulate](sm-workflow-Simulate.md) | Starts a workflow in simulation mode. |
| [SimulateWithParameters](sm-workflow-SimulateWithParameters.md) | Starts a workflow in simulation mode and provides it with parameters. |
| [Spawn](sm-workflow-Spawn.md) | Creates a workflow instance from a template, applies a patch then starts this workflow. |
| [SpawnWithParameters](sm-workflow-SpawnWithParameters.md) | Creates a workflow instance from a template then invokes the  [StartWithParameters](sm-workflow-StartWithParameters.md)  method on this instance. |
| [SpawnWithParametersEx](sm-workflow-SpawnWithParametersEx.md) | Creates a workflow instance from a model, and invoke the method  [StartWithParameters](sm-workflow-StartWithParameters.md)  or  [SimulateWithParameters](sm-workflow-SimulateWithParameters.md)  on this instance. |
| [Start](sm-workflow-Start.md) | Starts or resumes execution of a workflow. |
| [StartWithParameters](sm-workflow-StartWithParameters.md) | Starts a workflow and provides it with parameters. |
| [Stop](sm-workflow-Stop.md) | Stops a workflow in progress. |
| [Wakeup](sm-workflow-Wakeup.md) | Forces the advance processing of all pending tasks. |
| [WakeupTask](sm-workflow-WakeupTask.md) | Forces the advance processing of one or more pending tasks. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
