# getUrl

Recovers a text content from a URL.

```text
getUrl (url [, timeout ])
```

## Parameters

**url** The address of the page to recover.

**timeout** Connection timeout. If the connection cannot be established within the given delay, an error is raised and the script is interrupted.

## Return value

A character string containing the text page.

## Remarks

The encoding of the returned string is the encoding specified by the response (Content-Type). If an error occurs during download or if the return code is other than 200 (OK), an error is raised and the script being executed is interrupted. Example:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

## Features

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
