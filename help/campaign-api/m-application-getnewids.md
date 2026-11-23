# getNewIds

Returns a list of IDs of the internal database keys.

```text
getNewIds (count [, sequence ])
```

## Parameters

**count** Number of IDs which the method must return.

**sequence** Name of the sequence to use.

## Return value

A table containing the list of IDs:

## Remarks

This method is equivalent to the NLWS.xtkSession.GetNewIds() and NLWS.xtkSession.GetNewIdsEx() SOAP methods while being more efficient.

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
