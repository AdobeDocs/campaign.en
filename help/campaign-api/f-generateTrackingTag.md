# generateTrackingTag

Automatically generates a JavaScript tag for web tracking.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Parameters

**request** The HttpServletRequest object

**tagid** A string of characters which represent the name of the personalized tagid. If it is empty, the function generates the tag based on path name.

**folder** A string of characters which represent the internal name of a folder. If it is empty, the tag is created in the default directory, i.e. "Web tracking tags".

## Return value

A string of characters which contains the JavaScript code to include.

## Remarks

The generated tag is based on the name of the webapp, html page, controler or more generally speaking, the path name if the tagid is not entered. The last parameter specifies the tag destination folder. To invoke the function, pass the request object as an argument. Note the use of &lt;%== since the function generates html code. Example:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Features

**Available in:**

* JSSP
* WebApp
