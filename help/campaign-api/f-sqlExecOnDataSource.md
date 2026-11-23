# sqlExecOnDataSource

Executes an SQL script on a data source.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Parameters

**query** The SQL query.

**dataSource** The data source.

**value1, ...** Variables of the SQL query.

## Return value

The number of records updated or inserted in an UPDATE or INSERT SQL command.

## Remarks

The authorized values for the data source can be:

* "" or "default" points to the Adobe Campaign database

* "nms:extAccount:InternalName" points to a datasource defined in the Adobe Campaign external accounts (FDA)

* "name" (name of the datasource) points to a data source defined in the instance configuration file (config-instance.xml) in the following form:

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Example:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

The optional variables set as parameters of this function are defined in [sqlGetString(query, value1, ...)](f-sqlGetString.md)

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
