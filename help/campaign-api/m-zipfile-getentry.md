# getEntry

Extracts a file from the archive.

```text
getEntry (filename)
```

## Parameters

**filename** Name of the file in the archive.

## Return value

The ⌐ [MemoryBuffer](c-memorybuffer.md) that contains the contents of the file.

## Remarks

The archive must have been opened with the ⌐[open()](m-zipfile-open.md) method before you can use this method. Otherwise, an exception is raised. Example: The following example extracts the dir/content.xml file from an archive and saves it to the /tmp/ folder.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
```

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
