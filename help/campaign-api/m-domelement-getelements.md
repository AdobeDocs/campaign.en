# getElements

Returns the list of child elements with the specified name, belonging to this element.

```text
getElements ( [tagName ])
```

## Parameters

**tagName** Name of elements searched for. If this parameter is ommitted, the function returns all child elements.

## Return value

Table containing the list of elements.

## Remarks

This method creates a new table for each call. It is therefore better to keep the table in a local variable rather than make several calls.

## Features

**Method of class:** [DOMElement](c-domelement.md)

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
