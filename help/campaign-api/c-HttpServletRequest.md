# HttpServletRequest (Class)

Represents the query of a client forwarded to a servlet.

There is only one instance of this address accessible via the `request`. variable.

## Methods

| Method | Description |
| --- | --- |
| [getHeader](m-HttpServletRequest-getHeader.md) | Returns an attribute defined in the query header. |
| [getParameter](m-HttpServletRequest-getParameter.md) | Returns the value of a query parameter. |
| [getRemoteAddr](m-HttpServletRequest-getRemoteAddr.md) | Returns the IP address of the client or the last proxy to have sent a request. |
| [getUTF8Parameter](m-HttpServletRequest-getUTF8Parameter.md) | Returns the value (coded in UTF-8) of a parameter of the query. |
| [getBodyAsString](m-HttpServletRequest-getBodyAsString.md) | Returns the body of the query in the form of a string of characters using query coding. |
| [forward](m-HttpServletRequest-forward.md) | Redirects the query towards another page without going via the client. |

## Properties

| Property | Description |
| --- | --- |
| [parameters](p-HttpServletRequest-parameters.md) | Returns the query parameters. |
| [cookies](p-HttpServletRequest-cookies.md) | Returns the cookies of the query. |
| [requestURI](p-HttpServletRequest-requestURI.md) | Returns the URL of the query. |
| [queryString](p-HttpServletRequest-queryString.md) | Returns the part of the query's URL which matches the parameters. |
| [scheme](p-HttpServletRequest-scheme.md) | Returns the name of the protocol used (HTTP, HTTPS, etc.) to access this page. |
| [serverName](p-HttpServletRequest-serverName.md) | Returns the name of the query server. |
| [serverPort](p-HttpServletRequest-serverPort.md) | Returns the port number used to contact the server. |
| [serverURL](p-HttpServletRequest-serverURL.md) | Returns the URL for accessing the server. |
| [servletPath](p-HttpServletRequest-servletPath.md) | Returns the section of the query's URL which matches the servlet. |
| [contextPath](p-HttpServletRequest-contextPath.md) | Returns the section of the query's URL which matches the context. |
| [pathInfo](p-HttpServletRequest-pathInfo.md) | Returns the additional information of the query's URL. |
| [method](p-HttpServletRequest-method.md) | Returns a string of characters containing the HTTP method used to call up this query (GET, HEAD, POST, etc.). |

## Features

**Available in:**

* JSSP
* WebApp
