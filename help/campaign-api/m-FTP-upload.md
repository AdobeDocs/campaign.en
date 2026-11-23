# upload

Download a file from a local file to an FTP server.

```text
upload (URL)
```

## Parameters

**URL** Server URL.

## Return value

None.

## Remarks

The URL must start with 'ftp:' Example:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
```

## Features

**Method of class:** [FTP](c-FTP.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
