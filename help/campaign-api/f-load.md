# load

> Warning:
>
> Access via file APIs is limited to the **var**, **sftp** and temporary folders of Adobe Campaign.

Loads and returns an entity corresponding to a given schema and key.

```text
load (key)
```

## Parameters

**key** A character string corresponding to the key of the entity.

## Return value

Returns the entity in the form of a JavaScript object.

## Remarks

load is not a global function but a schema method. To invoke it, you must prefix it by the desired schema. For example:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

The properties and sub-properties of this object can be modified at will. Unlike the [get()](f-get.md) method, the document is not automatically saved in the database, you must invoke the [save()](m-Entity-save.md) method on the object. If the entity is not found in the database, it is an error and the script is interrupted.

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
