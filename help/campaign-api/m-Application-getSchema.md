# getSchema

Returns a mapping to an Adobe Campaign schema or null if the schema doesn't exist.

```text
getSchema (name [, checkIfUpdated ])
```

## Parameters

**name** Full schema name.

**checkIfUpdated** Check if the schema has been updated in the cache. No impact if the schema has already been instanced in the script.

## Return value

A schema mapping (refer to [Schema](c-Schema.md) object) or the method launches an exception is no schema coincides with the name.

## Remarks

All schemas instanciated in a script remain allocated in the memory until the end of the script. Example:

```javascript
      var schema = application.getSchema("nms:recipient")
```

## Features

**Method of class:** [Application](c-Application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
