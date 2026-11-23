# toBase64

Converts the buffer or part of the character string encoded in base 64.

```text
toBase64 ( [start ] [, length ])
```

## Parameters

**start** Number of bytes to ignore at the start of the buffer. The first byte corresponds to the value 0 (default value).

**length** Number of bytes to convert. By default, all the remaining bytes are taken into account.

## Return value

The content of the buffer encoded in base 64.

## Features

**Method of class:** [MemoryBuffer](c-memorybuffer.md)

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
