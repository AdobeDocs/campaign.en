# removeAll

Deletes all entities from the collection.

```text
removeAll ()
```

## Parameters

None.

## Return value

None.

## Remarks

Example:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## Features

**Method of class:** [EntityCollection](c-EntityCollection.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
