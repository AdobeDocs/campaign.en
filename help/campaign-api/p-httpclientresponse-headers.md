# headers

The list of headers for the HTTP response grouped by name.

```text
headers
```

## Remarks

Each headers property carried the name of the header and the value of the table that matches each header with this name. This function is different from [header](p-httpclientresponse-header.md) because it returns a table of values instead of a unique value for a given name. This is useful for headers that can appear several times, such as Accept-Language or Set-Cookie. The function returns an empty table if the HTTP response does not have a header with this name. Example:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

headers properties aren't itemizable. Property names aren't case sensitive.

## Features

**Property of class:** [HttpClientResponse](c-httpclientresponse.md)

**Read only:**

Yes

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
