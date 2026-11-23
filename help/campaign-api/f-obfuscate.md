# obfuscate

Obfuscates an integer into a character string. The original value can be recovered by calling [unobfuscate](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Parameters

**value** The integer to obfuscate.

**size** The size of the string resulting from obfuscation. An integer between 6 and 10. 6 by default.

**version** The obfuscation version to apply. 0 by default.

## Return value

A character string that represents the obfuscated integer.

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
