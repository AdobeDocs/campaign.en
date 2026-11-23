# StartWithParameters

Starts a workflow and provides it with parameters.

```text
StartWithParameters ( String workflowId, XML parameters )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

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

None.

## Remarks

The command is executed asynchronously, it has no immediate effect after the return of the method.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
