# findNode

Returns an instance of [SchemaNode](c-SchemaNode.md) or null if the node doesn't exist and the mustExist parameter is set to false.

```text
findNode (name [, strict ] [, mustExist ])
```

## Parameters

**name** XPath represents the name of the node to be searched

**strict** Boolean that indicates whether (strict to false) or not, when the name of the last item in the path does not exist as is, it shouls be searched for as an attribute or an element. By default to true.

**mustExist** Boolean that indicates whether an exception must be raised if the node does not exist. true by default.

## Return value

Returns a [SchemaNode](c-SchemaNode.md) instance if the node can be found, or null if the mustExist parameter is set to false.

## Remarks

Example:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Result:

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Features

**Method of class:** [SchemaNode](c-SchemaNode.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
