# getElementsByTagNameNS

Returns the list of all the document elements with the specified name and namespace.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Parameters

**namespaceURI** Namespace URI.

**localName** Name of searched for elements.

## Return value

Table containing the list of elements.

## Remarks

This method creates a new table for each call. It is therefore better to keep the table in a local variable rather than make several calls.

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
