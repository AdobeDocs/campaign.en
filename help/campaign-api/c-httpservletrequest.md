# HttpServletRequest (Class)

Represents the query of a client forwarded to a servlet.

There is only one instance of this address accessible via the `request`. variable.

## Methods

| Method | Description |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Returns an attribute defined in the query header. |
| [getParameter](m-httpservletrequest-getparameter.md) | Returns the value of a query parameter. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | Returns the IP address of the client or the last proxy to have sent a request. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | Returns the value (coded in UTF-8) of a parameter of the query. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Returns the body of the query in the form of a string of characters using query coding. |
| [forward](m-httpservletrequest-forward.md) | Redirects the query towards another page without going via the client. |

## Properties

| Property | Description |
| --- | --- |
| [parameters](p-httpservletrequest-parameters.md) | Returns the query parameters. |
| [cookies](p-httpservletrequest-cookies.md) | Returns the cookies of the query. |
| [requestURI](p-httpservletrequest-requesturi.md) | Returns the URL of the query. |
| [queryString](p-httpservletrequest-querystring.md) | Returns the part of the query's URL which matches the parameters. |
| [scheme](p-httpservletrequest-scheme.md) | Returns the name of the protocol used (HTTP, HTTPS, etc.) to access this page. |
| [serverName](p-httpservletrequest-servername.md) | Returns the name of the query server. |
| [serverPort](p-httpservletrequest-serverport.md) | Returns the port number used to contact the server. |
| [serverURL](p-httpservletrequest-serverurl.md) | Returns the URL for accessing the server. |
| [servletPath](p-httpservletrequest-servletpath.md) | Returns the section of the query's URL which matches the servlet. |
| [contextPath](p-httpservletrequest-contextpath.md) | Returns the section of the query's URL which matches the context. |
| [pathInfo](p-httpservletrequest-pathinfo.md) | Returns the additional information of the query's URL. |
| [method](p-httpservletrequest-method.md) | Returns a string of characters containing the HTTP method used to call up this query (GET, HEAD, POST, etc.). |

## Features

**Available in:**

* JSSP
* WebApp
