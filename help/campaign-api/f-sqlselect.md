# sqlSelect

Executes an SQL query and returns the result as an XML document.

```text
sqlSelect (format, query [, dataSource ])
```

## Parameters

**format** A string separated with commas describing the format of expected data as a name:type\[:length\] type list docName, \[fieldXPath:type,\]\*

**query** The SQL query.

**dataSource** The data source.

## Return value

An XML object containing a list of elements for each line of the query result.

## Remarks

Example:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
