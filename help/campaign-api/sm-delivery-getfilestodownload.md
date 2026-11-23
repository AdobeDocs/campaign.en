# GetFilesToDownload

Returns the list of files found on the server associated with the delivery.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Parameters

**deliveryId** Delivery identifier

## Return value(s)

**filesToDownload** Returns the list of files which can be downloaded as element \[properties/filesToDownload\]

**filesNotToDownload** Returns the list of files which cannot be downloaded as element \[properties/filesNotToDownload\]

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
