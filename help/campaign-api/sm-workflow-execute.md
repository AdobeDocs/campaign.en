# Execute

Executes a workflow immediately and waits for it to finish.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Parameters

**workflowId** Identifier or internal name of the workflow.

**simulationMode** Execution simulation.

**keepResult** Keep interim results.

**logSQL** Is it necessary to save a trace of SQL orders?

## Return value(s)

**workflow** The execution result.

## Features

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**Static:**

Yes
