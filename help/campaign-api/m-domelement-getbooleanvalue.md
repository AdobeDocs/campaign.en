# getBooleanValue

Returns the bolean node value referenced by the given XPath.

```text
getBooleanValue (xpath)
```

## Parameters

**xpath** Path.

## Return value

true if the text value of the referenced node is 'true' or '1', false is the value is 'false' or '0'.

## Remarks

The syntax for the XPath only accepts an XPath language subset. The value test is not case sensitive. An exception is raised if the path is badly formed or if the value is not a valid boolean.

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
