# remove

Deletes an entity from the collection.

```text
remove (index|object)
```

## Parameters

**index\|object** Index of the entity to delete or the entity itself.

## Return value

None.

## Remarks

Examples:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
delivery.save()
```

## Features

**Method of class:** [EntityCollection](c-entitycollection.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
