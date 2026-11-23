# copyTo

Copies a file.

```text
copyTo (fileName)
```

## Parameters

**fileName** Name of the target file or folder (must be full path).

## Return value

None.

## Remarks

Examples:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
```

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
