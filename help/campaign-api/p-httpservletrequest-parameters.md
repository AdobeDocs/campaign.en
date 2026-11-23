# parameters

Returns the query parameters.

```text
parameters
```

## Remarks

The parameters property returns an object with properties matching a parameter of the query. Example:

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
document.write(name + " : " + value + "<br>")
}
```

## Features

**Property of class:** [HttpServletRequest](c-httpservletrequest.md)

**Read only:**

Yes

**Available in:**

* JSSP
* WebApp
