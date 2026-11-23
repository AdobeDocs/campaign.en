# FilesExist

Checks if files already exist on server (as files or in the resource table).

```text
XML exist = FilesExist ( XML files )
```

## Parameters

**files** List of files (@name) and their MD5 keys (@md5) and Boolean indicating if it can be a resource (@checkResource).

## Return value(s)

**exist** List of results (@md5 and @exists)

## Features

**Schema:** [xtk:job](s-xtk-job.md)

**Static:**

Yes
