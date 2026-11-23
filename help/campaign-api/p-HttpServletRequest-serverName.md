# serverName

Returns the name of the query server.

```text
serverName
```

## Remarks

Example: The serverName of the following URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

returns the following string:

```javascript
adobe.com
```

## Features

**Property of class:** [HttpServletRequest](c-HttpServletRequest.md)

**Read only:**

Yes

**Available in:**

* JSSP
* WebApp
