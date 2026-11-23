# escapeUrl

Converts a character string to insert it in a URL.

```text
escapeUrl (value)
```

## Parameters

**value** Character string to convert.

## Return value

The character string after conversion.

## Remarks

The function transforms non-alphanumeric characters other than $-\_.\!\*'(),?/:@&amp;= into the corresponding hexadecimal value. The function complies with the RFC1738 specification and only allows you to encode ISO-Latin characters. To encode UTF-8 characters, use the encodeURIComponent() JavaScript function. Example:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
