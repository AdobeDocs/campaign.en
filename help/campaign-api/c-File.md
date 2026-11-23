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
| [File](m-File-File.md) | Creates a new object associated with a file. |
| [close](m-File-close.md) | Closes the file. |
| [copyTo](m-File-copyTo.md) | Copies a file. |
| [dispose](m-File-dispose.md) | Frees the resources used by the object. |
| [flush](m-File-flush.md) | Forces writing on the disk |
| [list](m-File-list.md) | Lists the content of a directory. |
| [mkdir](m-File-mkdir.md) | Creates a directory with the path of the current  [File](c-File.md)  object. |
| [open](m-File-open.md) | Opens the file in read or write mode. |
| [remove](m-File-remove.md) | Deletes the file. |
| [renameTo](m-File-renameTo.md) | Renames a file. |
| [readln](m-File-readln.md) | Reads a line of the text file. |
| [rmdir](m-File-rmdir.md) | Deletes the directory (not in cascade). |
| [writeln](m-File-writeln.md) | Writes a line of text to the file. |

## Properties

| Property | Description |
| --- | --- |
| [canRead](p-File-canRead.md) | Returns true if the file can be read. |
| [canWrite](p-File-canWrite.md) | Returns true if the file can be modified. |
| [exists](p-File-exists.md) | Returns true if there is a file or folder with this name. |
| [fullName](p-File-fullName.md) | Returns the name of the file in absolute. |
| [isDirectory](p-File-isDirectory.md) | Returns true if the file is a directory. |
| [isFile](p-File-isFile.md) | Returns true if the file exists and is a file. |
| [isOpen](p-File-isOpen.md) | Returns true if the file is open. |
| [lastModified](p-File-lastModified.md) | Returns the last modification date in the form of a Date object. |
| [name](p-File-name.md) | Returns the name of the file with the extension, but without the path. |
| [path](p-File-path.md) | Returns the complete path of the file ended by the separator. |
| [size](p-File-size.md) | Returns the size of the file in bytes. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
