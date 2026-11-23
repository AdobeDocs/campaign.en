# ZipFile

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

Creates a new Zip object associated with a file.

```text
ZipFile (filename)
```

## Parameters

**filename** The name of the archive to load or to create.

## Return value

None.

## Remarks

Example:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
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
