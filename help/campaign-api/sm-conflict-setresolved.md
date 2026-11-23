# SetResolved

Declares an entity as having no more conflicts.

```text
SetResolved ( String conflictId )
```

## Parameters

**conflictId** Conflict identifier.

## Return value(s)

None.

## Remarks

When all the conflicts are resolved, this method enables you to put the entity back in its normal place. All the conflicting attributes and elements must be resolved before invoking this method.

## Features

**Schema:** [xtk:conflict](s-xtk-conflict.md)

**Static:**

Yes
