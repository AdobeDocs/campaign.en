# loadLibrary

Loads a JavaScript library.

```text
loadLibrary (filename [, boolean ])
```

## Parameters

**filename** The name of the JavaScript library to load.

**boolean** Enables or disables the load cache. By default is true.

> Note: When the parameter is set to false, you need to use the logon() function before the loadLibrary call to be authenticated as operator.

## Return value

None.

## Remarks

The cache is enabled by default. If the cache is disabled, the database is queried for each call. This query lets you load the latest version of the library. Example: loadLibrary('xtk:shared/nl.js')

## Features

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
