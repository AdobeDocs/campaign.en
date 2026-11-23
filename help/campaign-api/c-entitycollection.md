# EntityCollection (Class)

Represents a collection of an entity.

Such an object cannot be instantiated directly. You must use the methods create(), get() or load().

The elements of a collection can be enumerated with `for` or `for each`. This example shows an enumeration of files linked to a delivery action.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Methods

| Method | Description |
| --- | --- |
| [add](m-entitycollection-add.md) | Adds a new entity to the collection. |
| [remove](m-entitycollection-remove.md) | Deletes an entity from the collection. |
| [removeAll](m-entitycollection-removeall.md) | Deletes all entities from the collection. |

## Properties

| Property | Description |
| --- | --- |
| [length](p-entitycollection-length.md) | Returns the entity number of the collection. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
