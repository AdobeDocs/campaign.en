# encryptDES

> Warning:
>
> This function is obsolete, use [cryptString()](f-cryptstring.md).

Encrypts a string with the DES algorithm.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parameters

**key** The key represented in hexadecimal. The key must be 64 bits long, i.e. 16 hexadecimal characters.

**value** The string to encrypt

**cipher mode** The method for coding blocks. A string of characters. i.e. "CBC", "ECB" or "EDE". By default "CBC".

**initialization vector** The initialization vector in the form of a hexadecimal string. Exactly 8 octets, i.e. 16 characters. An empty string by default.

**padding** The type of padding. A string of characters, i.e. "PKCS5PADDING" or "PKCS7PADDING". By default an empty string, which means that '\\0' is added at the end of the string to encrypt.

## Return value

The encrypted string represented in base 64.

## Remarks

* A DES key has 56 useful bits and 8 bits used for parity; These bits are ignored.
* The value effectively encrypted by the DES algorithm will be the 8-bit Windows-1252 representation of the string, finishing with an ASCII 0 character and padded to multiple of 64 bits with binary zeros.
* The encrypted value will be a multiple of 64-bit words.

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
