# DESencrypt

> Warning:
>
> This function is obsolete, use [cryptString()](f-cryptstring.md).

Digitizes a string with the DES algorithm.

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parameters

**value** The string to digitize

**key** The key represented in hexadecimal. The key must be 64 bits long, or 16 hexadecimal characters. By default, the identifier of the database is used.

**cipher mode** The blocks encoding method. One character string. i.e. "CBC", "ECB" or "EDE". By default "CBC".

**initialization vector** The initialization vector in the form of a hexadecimal string. Exactly 8 octets, i.e. 16 characters. An empty string by default.

**padding** The padding type. A character string, i.e. "PKCS5PADDING" or "PKCS7PADDING". By default, an empty string, which means that a '\\0' is added to the end of the string to be encrypted.

## Return value

The digitized string represented in base 64.

## Remarks

* A DES key has 56 useful bits and 8 bits used for parity; These bits are ignored.
* The value effectively encrypted by the DES algorithm will be the 8-bit Windows-1252 representation of the string, finishing with an ASCII 0 character and padded to multiple of 64 bits with binary zeros.
* The digitized value has multiple-length 64 bit value.

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
