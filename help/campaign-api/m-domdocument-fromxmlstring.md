# fromXMLString

Creates a new document from a string of XML characters.

```text
fromXMLString (string)
```

## Parameters

**string** String of XML characters.

## Return value

None.

## Remarks

An exception is raised if the argument is not a valid XML document. This function applies to the DOMDocument class. Example:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
```

## Features

**Method of class:** [DOMDocument](c-domdocument.md)

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
