# loadXmlFile

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

This function is obsolete, use [DOMDocument.load()](m-DOMDocument-load.md). Loads a file in the form of an XML document object

```text
loadXmlFile (filename [, noErr ])
```

## Parameters

**filename** The full name of the file to be loaded.

**noErr** If true, no error if the file is empty (default=false).

## Return value

An XML document.

## Remarks

This function supports the detection of the file's codepage thanks to the detection of BOM and the XML prologue.

## Features

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
