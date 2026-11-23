# File (Class)

File class

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

Here is an example of how to use the class to read and process all the lines of a file in sequence.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Methods

| Method | Description |
| --- | --- |
| [File](m-file-file.md) | Creates a new object associated with a file. |
| [close](m-file-close.md) | Closes the file. |
| [copyTo](m-file-copyto.md) | Copies a file. |
| [dispose](m-file-dispose.md) | Frees the resources used by the object. |
| [flush](m-file-flush.md) | Forces writing on the disk |
| [list](m-file-list.md) | Lists the content of a directory. |
| [mkdir](m-file-mkdir.md) | Creates a directory with the path of the current  [File](c-file.md)  object. |
| [open](m-file-open.md) | Opens the file in read or write mode. |
| [remove](m-file-remove.md) | Deletes the file. |
| [renameTo](m-file-renameto.md) | Renames a file. |
| [readln](m-file-readln.md) | Reads a line of the text file. |
| [rmdir](m-file-rmdir.md) | Deletes the directory (not in cascade). |
| [writeln](m-file-writeln.md) | Writes a line of text to the file. |

## Properties

| Property | Description |
| --- | --- |
| [canRead](p-file-canread.md) | Returns true if the file can be read. |
| [canWrite](p-file-canwrite.md) | Returns true if the file can be modified. |
| [exists](p-file-exists.md) | Returns true if there is a file or folder with this name. |
| [fullName](p-file-fullname.md) | Returns the name of the file in absolute. |
| [isDirectory](p-file-isdirectory.md) | Returns true if the file is a directory. |
| [isFile](p-file-isfile.md) | Returns true if the file exists and is a file. |
| [isOpen](p-file-isopen.md) | Returns true if the file is open. |
| [lastModified](p-file-lastmodified.md) | Returns the last modification date in the form of a Date object. |
| [name](p-file-name.md) | Returns the name of the file with the extension, but without the path. |
| [path](p-file-path.md) | Returns the complete path of the file ended by the separator. |
| [size](p-file-size.md) | Returns the size of the file in bytes. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
