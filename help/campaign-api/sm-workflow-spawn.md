# Spawn

Creates a workflow instance from a template, applies a patch then starts this workflow.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## Parameters

**workflowId** Identifier or internal name of the workflow template.

**patch** The XML element that must be merged with the model to obtain the instance before executing it. Example:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

This example replaces the arguments of the 'notepad' activity. If you do not want to apply this patch, use an empty &lt;workflow/&gt; element or an empty string.

## Return value(s)

**instanceId** Identifier of the instance created from the template.

## Remarks

The command is executed in asynchronous mode and does not have an immediate effect after the return of the method. The workflow is started with the account of the calling operator.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
