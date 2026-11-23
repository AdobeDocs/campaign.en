# getDateValue

Returns the date+hour type value of the node reference by the given XPath.

```text
getDateValue (xpath)
```

## Parameters

**xpath** Path.

## Return value

A Date type object matching the value of the node referenced.

## Remarks

The syntax for the XPath only accepts an XPath language subset. An exception is raised if the path is badly formed or if the value is not a valid date.

## Features

**Method of class:** [DOMElement](c-DOMElement.md)

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
