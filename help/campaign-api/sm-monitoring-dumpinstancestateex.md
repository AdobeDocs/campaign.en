# DumpInstanceStateEx

Return statuses of server processes

```text
XML monitoring = DumpInstanceStateEx ( String mask, Boolean includeDead, Boolean noDatabaseCheck, Number criticalLevel )
```

## Parameters

**mask** Mask for instances to consider

**includeDead** Add list of dead processes

**noDatabaseCheck** Does not check alerts from database objects

**criticalLevel** Filters severity of returned alerts

## Return value(s)

**monitoring**

## Features

**Schema:** [nl:monitoring](s-nl-monitoring.md)

**Static:**

Yes
