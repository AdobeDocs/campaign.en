# list

Returns the list of files on the server in a specified directory.

```text
list (URL, pattern [, max ])
```

## Parameters

**URL** Address of the FTP server as a URL.

**pattern** File and mask of the list of files to retrieve.

**max** Maximum number of files to return. If this parameter is missing, the method will return the full list of files.

## Return value

A table containing the file names corresponding to the specified path and mask.

## Remarks

If the FTP command fails, and exception is raised. Example:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
```

## Features

**Method of class:** [FTP](c-ftp.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
