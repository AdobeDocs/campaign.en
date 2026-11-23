# cryptString

> Warning:
>
> This function is fully deprecated. For more details, please refer to this [page](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Encrypts a string of characters with the key of the instance or any other key.

```text
cryptString (str [, key ] [, useSalt ])
```

## Parameters

**str** The character string to encrypt.

**key** The AES encryption key is encoded in base 64: 256 bits if key length is 32; 192 bits if the key length is 24; 128 bits if the key length is 16 or if no key is specified.

**useSalt** Use a salt of the data to encrypt. True by default.

## Return value

Returns the encrypted character string

## Remarks

Encryption takes place according to the following method:

* The unicode character string is transformed into a UTF-8 string.
* A check character is added at the end.
* This string is encrypted using the AES algorythm in Cipher Block Chaining (CBC) mode with a null initialization vector. If no key is provided as a parameter, the instance key is used.
* The encrypted block is then converted into base 64.

Decryption is carried out using the [decryptString](f-decryptString.md) function.

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
