# WorkflowTask (Class)

Status of a workflow task.

A ⌐`WorkflowTask` is a class that cannot be instanciated and for which there is only one single instance accessible in the workflow activities called `task`.

## Methods

| Method | Description |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Flags the task as finished. |
| [postEvent](m-workflowtask-postevent.md) | Activates a transition. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Forces the next date of processing by the task. |
| [doneTransition](m-workflowtask-donetransition.md) | Returns the "done" transition of the activity. |
| [errorTransition](m-workflowtask-errortransition.md) | Returns the "error" transition of the activity. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Returns the transition corresponding to the given type. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Returns the transitions corresponding to the given name. |
| [transitions](m-workflowtask-transitions.md) | Returns the list of transitions of the activity. |
| [wait](m-workflowtask-wait.md) | Awaits a signal. |

## Features

**Available in:**

* Workflow
