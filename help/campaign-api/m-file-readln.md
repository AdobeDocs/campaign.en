# readln

Reads a line of the text file.

```text
readln ()
```

## Parameters

None.

## Return value

The string containing the next line of the file or ⌐null if the end of file is reached.

## Remarks

Example:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
f.close()
```

## Features

**Method of class:** [File](c-file.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
