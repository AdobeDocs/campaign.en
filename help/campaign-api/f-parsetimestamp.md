# parseTimeStamp

Converts a character string containing a date formulated based on a simplified version of the ISO 8601 standard into a Date type object.

```text
parseTimeStamp (aString)
```

## Parameters

**aString** The date as a character string in ISO 8601 format.

## Return value

A Date type object that matches the date set as a parameter.

## Remarks

The syntax is as follows:

```javascript
              date
              time[time-zone]
            
```

or

```javascript
              dateTtime[time-zone]
            
```

The date must have the following format:

```javascript
YYYY-MM-DD
```

For compatibility reasons, the following format is also accepted:

```javascript
YYYY/MM/DD
```

The time must have the following format:

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

The time zone, if specified, must have the following format:

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

If the time zone isn't specified, the date will be converted into the current time zone (depending on context). Examples:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

If the date format isn't valid, an exception is raised.

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
