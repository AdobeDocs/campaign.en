# enumerations

Returns the table which contains the list of [enumerations](c-Enumeration.md) defined in this schema.

```text
enumerations
```

## Remarks

Example:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Features

**Property of class:** [Schema](c-Schema.md)

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
