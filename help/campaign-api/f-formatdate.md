# formatDate

Formats a date as a character string.

```text
formatDate (date, format [, timeZone ])
```

## Parameters

**date** The date to convert.

**format** The character string describing the format to use. The characters used to format the different parts of the date are the following:

* Y - Year
* M - Month of the year (1-12)
* B - Month name
* D - Day of the month (1-31)
* A - Day name
* J - Day of the year (1-366)
* W - Week of the year
* H - Hour (0-23)
* I - Hour (1-12)
* N - Minutes (0-59)
* S - Seconds (0-59)
* P - AM/PM

You can specify a number in front of certain of these characters. The A and B characters can be followed by a l to use the full name rather than the shortened version or a i to use the name in English. Examples:

* "%4Y/%2M/%2D" =&gt; 2000/01/24.
* "%A %D %B %4Y" =&gt; mon 24 jan 2000.
* "%Al %D %Bl %4Y" =&gt; monday 24 january 2000.
* "%02H:%02N:%02S" displays the hour, minutes and seconds to two figures.

**timeZone** String of characters corresponding to the timezone. Possible values are specified in the xtk:common:timezone enumeration schema.

## Return value

A character string representing the date in the requested format.

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
