# joinParts

Returns a table of SchemaNode instances for which each element represents a condition of the join.

```text
joinParts
```

## Remarks

Each element in the table has two properties:

* source - The element which represents the field of the source table.
* destination - The element which represents the field of the destination table.

Example:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## Features

**Property of class:** [SchemaNode](c-SchemaNode.md)

**Read only:**

Yes

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
