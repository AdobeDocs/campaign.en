# add

Adds a new entity to the collection.

```text
add ( [index ], xml)
```

## Parameters

**index** The entity will be added at this index point. If this argument is not specified, the entity will be appended to the end of the list.

**xml** The entity to insert in XML form.

## Return value

The element created.

## Remarks

The following example shows two different ways to add a new element to a collection. The first solution passes the full definition of the element to the add() method, whereas the second one passes and empty &lt;attachment/&gt; element then assigns the attributes in the normal way.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

The two solutions are equivalent, but the second one enables you to use the JavaScript types corresponding to attribute types whereas the first one only supports strings.

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
