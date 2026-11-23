# sqlGetDateOnDataSource

Returns the date resulting from an SQL query on a data source.

```text
sqlGetDateOnDataSource (query, dataSource [, value1, ... ])
```

## Parameters

**query** The SQL query.

**dataSource** The data source.

**value1, ...** Variables of the SQL query.

## Return value

The date type value that matches the query.

## Remarks

The "data source" parameter is defined in the [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlExecOnDataSource.md) function The optional variables that are parameters of this function are defined in [sqlGetString(query, value1, ...)](f-sqlGetString.md)

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
