# queryString

Returns the part of the query's URL which matches the parameters.

```text
queryString
```

## Remarks

Example: The queryString of the following URL:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

returns the following string:

```javascript
id=1234&param=dummy
```

## Features

**Property of class:** [HttpServletRequest](c-HttpServletRequest.md)

**Read only:**

Yes

**Available in:**

* JSSP
* WebApp
