# WebPostUpload

Finalize the storage of the resource after the upload (from a web page) to the server depending on the storage type used. Recovers the codepage and the content type.

```text
fileRes.WebPostUpload ( XML params )
```

## Parameters

**params** For 'workspace' type storage: @formerFileName contains the previous name in the workspace. If you want to save the entity immediately: @immediateSave must be set to 'true'

## Return value(s)

None.

## Features

**Schema:** [xtk:fileRes](s-xtk-fileres.md)

**Static:**

No

**Const:**

No

**Key only:**

No
