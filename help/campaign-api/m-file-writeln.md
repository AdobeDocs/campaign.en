# writeln

Writes a line of text to the file.

```text
writeln (line)
```

## Parameters

**line** The text line to write.

## Return value

None.

## Remarks

Example:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
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
