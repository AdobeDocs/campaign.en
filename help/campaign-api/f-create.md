# create

Creates a new entity corresponding to a given schema.

```text
create ( [content ])
```

## Parameters

**content** An optional character string corresponding to the XML of the entity to create.

## Return value

Returns the entity in the form of a JavaScript object.

## Remarks

create is not a global function but a schema method. To invoke it, you must prefix it by the desired schema. For example:

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

The document is not automatically saved to the database. You must use the ⌐⌐[save()](m-Entity-save.md) method on the entity.

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
