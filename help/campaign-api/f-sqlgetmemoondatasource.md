# sqlGetMemoOnDataSource

Returns the Memo field resulting from an SQL query on a data source.

```text
sqlGetMemoOnDataSource (query, dataSource [, value1, ... ])
```

## Parameters

**query** The SQL query.

**dataSource** The data source.

**value1, ...** Variables of the SQL query.

## Return value

The Memo field that matches the query.

## Remarks

The "data source" parameter is defined in the [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md) function The optional variables set as parameters of this function are defined in [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
