# saveXmlString

This command is deprecated, use [saveXmlFile()](f-savexmlfile.md). Saves a character string corresponding to an XML document to a file.

```text
saveXmlString (text, filename [, codePage ])
```

## Parameters

**text** The XML document in the form of a character string to save.

**filename** The full name of the file to save.

**codePage** This optional parameter enables you to specify the character encoding. Example:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Return value

None.

## Remarks

This function inserts an XML prolog in the file, if necessary, and specifies the document coding. If the character encoding is not specified, the server default is used.

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
