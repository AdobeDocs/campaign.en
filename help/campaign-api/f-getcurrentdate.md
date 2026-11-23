# getCurrentDate

Returns the current date of the database server.

```text
getCurrentDate ()
```

## Parameters

None.

## Return value

The current date of the database server.

## Remarks

Example:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

For more on the formatDate() function, refer to [formatDate(date, format)](f-formatdate.md)

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
