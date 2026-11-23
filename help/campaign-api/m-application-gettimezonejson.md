# getTimezoneJson

Returns a string of characters which is the JSON representation of the list of time differences with UTC time and their start date compared to the UNIX period for a time zone.

```text
getTimezoneJson ( [timezone ])
```

## Parameters

**timezone** The name of the time zone for which you need to return the list of time differences compared with UTC. Each time difference is linked to a start date applicable until the next start date. If no value is returned, uses the default operator time zone.

## Return value

Returns a character string which is the JSON representation of the time differences to apply based on the dates. The JSON string returned is assessed in a table of {startDate, offset} couples. The returned character string has the following form:

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate is the Posix time starting from which the lapse applies.
* offset is the value in milliseconds of the time difference with UTC. For instance UTC+02:00 equals 7200000.

## Remarks

getTimezoneJson is called via the application instance.

```javascript
var tzList = eval(application.getTimezoneJson());
```

## Features

**Method of class:** [Application](c-application.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
