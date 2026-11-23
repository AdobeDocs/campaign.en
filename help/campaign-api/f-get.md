# get

Loads and returns an entity corresponding to a given schema and key.

```text
get ( [key or content ])
```

## Parameters

**key or content** A character string corresponding to the key of the entity of XML content to create or initiate a new entity.

## Return value

Returns the entity in the form of a JavaScript object.

## Remarks

get is not a global function but a schema method. To invoke it, you must prefix it by the desired schema. For example:

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

The properties and sub-properties of this object can be modified at will. The document is automatically saved in the database when the script finishes execution if it is modified. If it is not a creation and the entity is not already in the database, it is an error and the script is interrupted.

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
