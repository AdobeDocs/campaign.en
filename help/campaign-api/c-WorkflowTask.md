# WorkflowTask (Class)

Status of a workflow task.

A ⌐`WorkflowTask` is a class that cannot be instanciated and for which there is only one single instance accessible in the workflow activities called `task`.

## Methods

| Method | Description |
| --- | --- |
| [setCompleted](m-WorkflowTask-setCompleted.md) | Flags the task as finished. |
| [postEvent](m-WorkflowTask-postEvent.md) | Activates a transition. |
| [setNextProcessingDate](m-WorkflowTask-setNextProcessingDate.md) | Forces the next date of processing by the task. |
| [doneTransition](m-WorkflowTask-doneTransition.md) | Returns the "done" transition of the activity. |
| [errorTransition](m-WorkflowTask-errorTransition.md) | Returns the "error" transition of the activity. |
| [transitionByType](m-WorkflowTask-transitionByType.md) | Returns the transition corresponding to the given type. |
| [transitionByName](m-WorkflowTask-transitionByName.md) | Returns the transitions corresponding to the given name. |
| [transitions](m-WorkflowTask-transitions.md) | Returns the list of transitions of the activity. |
| [wait](m-WorkflowTask-wait.md) | Awaits a signal. |

## Features

**Available in:**

* Workflow
