# getHeader

Returns an attribute defined in the query header.

```text
getHeader (name)
```

## Parameters

**name** Name of the header's attribute.

## Return value

None.

## Remarks

Example:

```javascript
Host: <%= request.getHeader("host") %>
```

## Features

**Method of class:** [HttpServletRequest](c-HttpServletRequest.md)

**Available in:**

* JSSP
* WebApp
