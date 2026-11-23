# fields

Returns a table which contains the field of fields ([SchemaNode](c-schemanode.md)) of the key.

```text
fields
```

## Remarks

Example:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
{
  logInfo("Key: " + key.name)
  for each(var field in key.fields)
    logInfo("\t" + field.name + "\t" + field.type)
}
    
```

## Features

**Property of class:** [SchemaKey](c-schemakey.md)

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
