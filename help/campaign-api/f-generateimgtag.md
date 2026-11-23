# generateImgTag

Enables the generation of an HTML &lt;img&gt; tag based on a public resource.

```text
generateImgTag (ID)
```

## Parameters

**ID** Public resource ID

## Return value

Returns the HTML &lt;img&gt; tag with the properties of the image contained in the public resource definition.

## Remarks

Resources must be published on frontal servers. Example:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
```

## Features

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
