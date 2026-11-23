# hmac

Calculates the MD5, SHA-1 or SHA-256 hash of the buffer.

```text
hmac (key [, algo ])
```

## Parameters

**key** Key, in the form of a buffer.

**algo** Hash type to use. The possible values are "MD5", "SHA1" or "SHA256. They are not case sensitive, the values can therefore be entered in lower case or upper case. By default, the value "SHA1" is selected if the parameter is not specified.

## Return value

The hash MD5, SHA-1 or SHA-256 (according to the hash type chosen) of the buffer.

## Features

**Method of class:** [MemoryBuffer](c-MemoryBuffer.md)

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
