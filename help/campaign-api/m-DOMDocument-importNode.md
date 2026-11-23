# importNode

Creates a node copy from another document.

```text
importNode (importedNode, deep)
```

## Parameters

**importedNode** Source node.

**deep** true if the full node must be copied, otherwise false.

## Return value

Copy of the node.

## Remarks

Example:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
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
