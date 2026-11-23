# open

Opens the file in read or write mode.

```text
open ( [mode ] [, codepage ])
```

## Parameters

**mode** File opening mode. The mode can be one of several values:

* "r" - Opens the file in read-only mode. This mode is the default mode.
* "w" - Opens the file in write mode.
* "a" - Opens the file in 'append' mode, the data written to the file is appended at the end.

**codepage** The file encoding. The encoding may be one of the following values:

* File.CODEPAGE\_CURRENT - This is the default codepage.
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_OEMLATIN1
* File.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## Return value

None.

## Remarks

If the file cannot be opened, an exception is raised.

## Features

**Method of class:** [File](c-File.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
