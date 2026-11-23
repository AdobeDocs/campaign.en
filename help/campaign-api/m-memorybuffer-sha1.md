# sha1

Computes the SHA-1 signature of the MemoryBuffer content.

```text
sha1 ()
```

## Parameters

None.

## Return value

A string of characters which is the hexadecimal representation of the SHA-1 signature.

## Remarks

Example:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

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
