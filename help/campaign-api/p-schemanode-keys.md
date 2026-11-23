# keys

Returns a table with definitions of the current node's [SchemaKey](c-schemakey.md) keys.

```text
keys
```

## Remarks

Example:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
```

## Features

**Property of class:** [SchemaNode](c-schemanode.md)

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
