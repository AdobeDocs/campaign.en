# hmacStr

Calculates the MD5, SHA-1 or SHA-256 hash of a string of characters. The string is automatically encoded in UTF-8 before the calculation.

```text
hmacStr (string [, key ] [, algo ])
```

## Parameters

**string** The string in which the hash is to be calculated.

**key** Key, in the form of a string of characters. It is automatically converted into UTF-8. If the key is missing, the server will use a key that depends on the instance and is only valid on this instance.

**algo** Type of hash to use. Possible values are "MD5", "SHA1" or "SHA256". Case is ignored, values can therefore be entered in lower case or upper case. The value "SHA1" is selected by default, if no parameter is specified.

## Return value

The MD5, SHA-1 or SHA-256 hash (depending on the type of hash selected) of the string passed as a parameter.

## Remarks

For MD5 and SHA-1 types, the key can be up to 64 characters (512 bits) after conversion into UTF-8. For the SHA-256 type, the key can be up to 32 characters (256 bits) after conversion into UTF-8.

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
