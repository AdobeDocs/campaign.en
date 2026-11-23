# isEqualNode

Compares two nodes.

```text
isEqualNode (arg)
```

## Parameters

**arg** The second node.

## Return value

true if the two nodes are equal, otherwise false.

## Remarks

Two nodes are equal if the following conditions are verified:

* The two nodes are the type type.
* nodeName, localName, namespaceURI, prefix and nodeValue properties must be identical.
* The two nodes are the type type.
* Attributes must be equal.
* Nodes must be equal.

As normalization can affect equality, we recommend you normalize before comparing.

## Features

**Method of class:** [DOMNode](c-DOMNode.md)

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
