# serverPort

Returns the port number used to contact the server.

```text
serverPort
```

## Remarks

Example: The serverPort of the following URL:

```javascript
http://adobe.com:8080/nms/test.jst
```

returns the following string:

```javascript
8080
```

The serverPort of the following URL:

```javascript
http://adobe.com/nms/test.jst
```

returns the following string:

```javascript
80
```

## Features

**Property of class:** [HttpServletRequest](c-HttpServletRequest.md)

**Read only:**

Yes

**Available in:**

* JSSP
* WebApp
