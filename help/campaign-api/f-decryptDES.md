# decryptDES

> Warning:
>
> This function is obsolete, use [decryptString()](f-decryptString.md).

Unencrypts a string with the DES algorithm.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## Parameters

**key** The key represented in hexadecimal. The key must be 64 bits long or 16 hexadecimal characters.

**value** The data to encrypt represented in base 64.

**cipher mode** The method for coding blocks. A string of characters. i.e. "CBC", "ECB" or "EDE". By default "CBC".

**initialization vector** The initialization vector in the form of a hexadecimal string. Exactly 8 octets, i.e. 16 characters. An empty string by default.

## Return value

The characters string in clear text.

## Remarks

* A DES key has 56 useful bits and 8 bits used for parity; These bits are ignored.
* The data will be unencrypted as an 8-bit string in the Windows-1252 codepage.
* The length of the encrypted data must be a multiple of 64 bits.

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
