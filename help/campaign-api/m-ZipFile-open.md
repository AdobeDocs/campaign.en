# open

Loads an existing archive.

```text
open ()
```

## Parameters

None.

## Return value

None.

## Remarks

In the case of an existing archive, you must first call the ⌐[fileCount](p-ZipFile-fileCount.md) method to recover the number of files or [getEntry()](m-ZipFile-getEntry.md) to extract a file. The method raises an exception if the file does not exist or if the file is not a valid archive.

## Features

**Method of class:** [ZipFile](c-ZipFile.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
