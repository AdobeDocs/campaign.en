# SpawnWithParameters

Creates a workflow instance from a template then invokes the [StartWithParameters](sm-workflow-startwithparameters.md) method on this instance.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Parameters

**workflowId** Identifier or internal name of the workflow template.

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
