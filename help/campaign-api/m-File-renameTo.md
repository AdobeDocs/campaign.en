# renameTo

Renames a file.

```text
renameTo (fileName)
```

## Parameters

**fileName** New file name (must be a full path).

## Return value

None.

## Remarks

Examples:

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
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
