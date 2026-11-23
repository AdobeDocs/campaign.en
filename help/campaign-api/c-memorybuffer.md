# MemoryBuffer (Class)

Represents a binary content stored in memory.

A is an intermediate object for manipulating data to and from a file.

## Methods

| Method | Description |
| --- | --- |
| [dispose](m-memorybuffer-dispose.md) | Frees the resources used by the object. |
| [load](m-memorybuffer-load.md) | Loads the content of a file into the buffer. |
| [save](m-memorybuffer-save.md) | Saves the content of the buffer to a file. |
| [toXML](m-memorybuffer-toxml.md) | Returns an XML JavaScript object obtained from the content of the  [MemoryBuffer](c-memorybuffer.md)  . This function is obsolete, use  [toDocument()](m-memorybuffer-todocument.md) |
| [toDocument](m-memorybuffer-todocument.md) | Returns an XML document from the text content of this buffer. |
| [toString](m-memorybuffer-tostring.md) | Returns the content of the  [MemoryBuffer](c-memorybuffer.md)  in the form of a string of characters. |
| [fromString](m-memorybuffer-fromstring.md) | Loads the contents of a character string in the buffer. |
| [toBase64](m-memorybuffer-tobase64.md) | Converts the buffer or part of the character string encoded in base 64. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Appends data from a character string encoded in base 64 to the end of the buffer. |
| [removeAll](m-memorybuffer-removeall.md) | Flushes the buffer. |
| [sha1](m-memorybuffer-sha1.md) | Computes the SHA-1 signature of the MemoryBuffer content. |
| [sha224](m-memorybuffer-sha224.md) | Computes SHA-2 224 bit signature of the MemoryBuffer content. |
| [sha256](m-memorybuffer-sha256.md) | Computes SHA-2 256 bit signature of the MemoryBuffer content. |
| [sha384](m-memorybuffer-sha384.md) | Computes SHA-2 384 bit signature of the MemoryBuffer content. |
| [sha512](m-memorybuffer-sha512.md) | Computes SHA-2 512 bit signature of the MemoryBuffer content. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Loads the content of a hexadecimal string in the buffer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Converts the buffer into a string of hexadecimal characters. |
| [hmac](m-memorybuffer-hmac.md) | Calculates the MD5, SHA-1 or SHA-256 hash of the buffer. |

## Properties

| Property | Description |
| --- | --- |
| [size](p-memorybuffer-size.md) | Returns the size of the buffer in bytes. |
| [isEmpty](p-memorybuffer-isempty.md) | Returns true if the buffer is empty. |

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
