# cookies

Returns the cookies of the query.

```text
cookies
```

## Remarks

The cookies property returns an object, with a matching cookie for each of its properties. Example:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
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
