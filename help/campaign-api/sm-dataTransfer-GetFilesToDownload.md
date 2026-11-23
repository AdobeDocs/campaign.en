# GetFilesToDownload

Returns the list of files used by this transfer and found on the server

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Parameters

**jobId** Transfer identifier

## Return value(s)

**filesToDownload** Returns the list of files which can be downloaded as an element \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** Returns the list of files which cannot be downloaded as an element \[dataTransfer/properties/filesNotToDownload\]

## Features

**Schema:** [xtk:dataTransfer](s-xtk-dataTransfer.md)

**Static:**

Yes
