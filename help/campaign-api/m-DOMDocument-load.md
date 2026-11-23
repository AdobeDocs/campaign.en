# load

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

Creates a new document from an XML file.

```text
load (filename [, allowEmpty ])
```

## Parameters

**filename** Name of the file to load.

**allowEmpty** If true, does not raise an exception if the file is empty (default=false).

## Return value

None.

## Remarks

An exceeption is raised if the file cannot be loaded or if the file content is not a valid XML document. This function applies to the DOMDocument class. Example:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## Features

**Method of class:** [DOMDocument](c-DOMDocument.md)

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
