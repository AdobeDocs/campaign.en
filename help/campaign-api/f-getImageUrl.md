# getImageUrl

Enables generation of the public resource access URL

```text
getImageUrl (ID|internal name)
```

## Parameters

**ID\|internal name** ID of the public resource or internal name of the resource.

## Return value

Returns the public resource access URL.

## Remarks

Resources must be published on frontal servers. Example:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
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
