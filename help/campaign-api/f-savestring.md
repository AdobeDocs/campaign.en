# saveString

This command is deprecated, use [saveFile()](f-savefile.md). Saves a character string to a file.

```text
saveString (text, filename [, codePage ])
```

## Parameters

**text** The text string to save.

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

If the character encoding is not specified, the server default is used.

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
