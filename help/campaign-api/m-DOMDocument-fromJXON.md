# fromJXON

Creates a new document from a JXON object.

```text
fromJXON (obj)
```

## Parameters

**obj** A JXON object representing the XML document to create.

## Return value

None.

## Remarks

Functions passing a DOMDocument or DOMElement as paramenter also directly accept a JXON object. Building an intermediary object using this function is not necessary. An exception is raised if the object is not a valid JXON object. This function applies to the DOMDocument class. Example:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
```

## Features

**Method of class:** [DOMDocument](c-DOMDocument.md)

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
