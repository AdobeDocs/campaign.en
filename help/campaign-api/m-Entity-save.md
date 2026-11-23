# save

Saves an entity in the database.

```text
save ()
```

## Parameters

None.

## Return value

None.

## Remarks

Example:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Features

**Method of class:** [Entity](c-Entity.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
