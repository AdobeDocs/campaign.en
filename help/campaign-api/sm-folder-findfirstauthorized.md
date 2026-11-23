# FindFirstAuthorized

Find the first eligible folder for the current user, satisfying the folderFilter condition.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Parameters

**folderFilter** Filter on folders

**writeAccess** The folder returned must be writable

**orgUnit** The folder returned must be compatible with the specified organizational entity

## Return value(s)

**folderEntity** Returns the associated folder entity (null is no folder found)

## Features

**Schema:** [xtk:folder](s-xtk-folder.md)

**Static:**

Yes
