# workflow

Workflows definitions

## Methods

| Method | Description |
| --- | --- |
| [Cleanup](sm-workflow-cleanup.md) | Purges workflow history. |
| [DeleteResult](sm-workflow-deleteresult.md) | Erases the results of one or more activities. |
| [Execute](sm-workflow-execute.md) | Executes a workflow immediately and waits for it to finish. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | Executes a workflow immediately and waits for it to finish. |
| [GetLogin](sm-workflow-getlogin.md) | Returns information from the execution account. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Returns the parameters of a workflow task in progress. |
| [Kill](sm-workflow-kill.md) | Unconditionally stops a workflow. |
| [Pause](sm-workflow-pause.md) | Suspends execution of a workflow in progress. |
| [PostEvent](sm-workflow-postevent.md) | Generates an event from any kind of activity. |
| [Reply](sm-workflow-reply.md) | Responds to a validation-type task in progress. |
| [Restart](sm-workflow-restart.md) | Links together a workflow stop and a workflow start. |
| [RestartTask](sm-workflow-restarttask.md) | Forces restarting of one or more finished tasks. |
| [SetLogin](sm-workflow-setlogin.md) | Changes the execution account. |
| [Simulate](sm-workflow-simulate.md) | Starts a workflow in simulation mode. |
| [SimulateWithParameters](sm-workflow-simulatewithparameters.md) | Starts a workflow in simulation mode and provides it with parameters. |
| [Spawn](sm-workflow-spawn.md) | Creates a workflow instance from a template, applies a patch then starts this workflow. |
| [SpawnWithParameters](sm-workflow-spawnwithparameters.md) | Creates a workflow instance from a template then invokes the  [StartWithParameters](sm-workflow-startwithparameters.md)  method on this instance. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Creates a workflow instance from a model, and invoke the method  [StartWithParameters](sm-workflow-startwithparameters.md)  or  [SimulateWithParameters](sm-workflow-simulatewithparameters.md)  on this instance. |
| [Start](sm-workflow-start.md) | Starts or resumes execution of a workflow. |
| [StartWithParameters](sm-workflow-startwithparameters.md) | Starts a workflow and provides it with parameters. |
| [Stop](sm-workflow-stop.md) | Stops a workflow in progress. |
| [Wakeup](sm-workflow-wakeup.md) | Forces the advance processing of all pending tasks. |
| [WakeupTask](sm-workflow-wakeuptask.md) | Forces the advance processing of one or more pending tasks. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-entity-save.md) | Saves an entity in the database. |
