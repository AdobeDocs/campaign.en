# escapeXmlStr

Converts a character string to XML format.

```text
escapeXmlStr (value)
```

## Parameters

**value** Character string to convert.

## Return value

The character string after conversion.

## Remarks

The function transforms the &amp;, &lt;, &gt; and \\" characters to the corresponding escape sequences:

* &amp; &amp;amp;
* &lt; &amp;lt;
* &gt; &amp;gt;
* " &amp;quot;

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
