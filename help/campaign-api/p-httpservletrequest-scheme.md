# scheme

Returns the name of the protocol used (HTTP, HTTPS, etc.) to access this page.

```text
scheme
```

## Remarks

Example: The scheme of the following URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

returns the following string:

```javascript
http
```

## Features

**Property of class:** [HttpServletRequest](c-httpservletrequest.md)

**Read only:**

Yes

**Available in:**

* JSSP
* WebApp
