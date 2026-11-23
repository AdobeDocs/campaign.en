# body

The body of the HTTP query.

```text
body
```

## Remarks

The object assigned to the body of the query is processed as follows:

* undefined, null, function: are not considered as sendable elements, the body of the HTTP query is empty.
* number, boolean, string, XML, Object: changed into a string of characters based on the toString method and encoded based on the HTTP header Content-type.
* [MemoryBuffer](c-memorybuffer.md): The content is copied in the body of the query without alteration.

Example:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
```

## Features

**Property of class:** [HttpClientRequest](c-httpclientrequest.md)

**Read only:**

No

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
