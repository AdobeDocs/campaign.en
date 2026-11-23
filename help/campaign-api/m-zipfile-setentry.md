# setEntry

Adds or updates a file in the archive.

```text
setEntry (filename, buffer)
```

## Parameters

**filename** Name of the source file.

**buffer** MemoryBuffer that contains the file.

## Return value

None.

## Remarks

The archive will not be effectively modified on the disk until the [save()](m-zipfile-save.md) method is called.

## Features

**Method of class:** [ZipFile](c-zipfile.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
