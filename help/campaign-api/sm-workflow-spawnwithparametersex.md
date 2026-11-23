# SpawnWithParametersEx

Creates a workflow instance from a model, and invoke the method [StartWithParameters](sm-workflow-startwithparameters.md) or [SimulateWithParameters](sm-workflow-simulatewithparameters.md) on this instance.

```text
Number instanceId = SpawnWithParametersEx ( String workflowId, Boolean simulation, XML parameters )
```

## Parameters

**workflowId** Identifier or internal name of the workflow template.

**simulation** If true, the newly created wotkflow is started in simulation mode.

**parameters** Parameters to pass to the instance. These parameters will become the instance variables of the workflow. This argument is an XML element whose name must be variables and may only include attributes. Example:

```xml
<variables foo="abc" bar="def">
```

The JavaScript scripts within the workflow may access these variables from the instance.vars object:

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Return value(s)

**instanceId** Identifier of the instance created from the template.

## Remarks

The command is executed in asynchronous mode and does not have an immediate effect after the return of the method. The workflow is started with the calling operators' account, except if a specific login is linked to the template in the workflow login table, in which case this login is used.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
