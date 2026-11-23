# loadFile

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

Returns the content of a text file

```text
loadFile (filename [, codePage ])
```

## Parameters

**filename** The full name of the file to load.

**codePage** This optional parameter enables you to specify the character encoding. Example:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Return value

A character string corresponding to the contents of the text file.

## Remarks

If the character encoding is not specified, the server default is used.

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
