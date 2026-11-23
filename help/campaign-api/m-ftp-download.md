# download

Downloads a file from the server to a local file or to memory.

```text
download (URL [, append ])
```

## Parameters

**URL** URL of the file to download.

**append** By default, if the downloaded file already exists on the local disk, it will be overwritten by the new file received. If the boolean is activated, then Adobe Campaign will write the downloaded content in the file with the same name along with the existing content.

## Return value

None.

## Remarks

To recover the file in a local file, start by using the setFile method. Example:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
