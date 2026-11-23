# list

Lists the content of a directory.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Parameters

**mask** The search mask (\* by default).

**sort** true to sort the result (false by default).

**noCase** true to ignore the class when sorting (false by default).

## Return value

A table containing the list of files ( [File](c-file.md) ) that match the specified path and mask.

## Remarks

The directory name must end with a / in Linux and a \\ in Windows. Example:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
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
