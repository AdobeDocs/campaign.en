# Application (Class)

This class has a single instance which provides access to certain properties of the applicative server. This singleton is accessible via the `application` global variable.

## Methods

| Method | Description |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Tests if a package is installed. |
| [getSchema](m-application-getschema.md) | Returns a mapping to an Adobe Campaign schema or null if the schema doesn't exist. |
| [getDBMSType](m-application-getdbmstype.md) | Returns the server type of the database. |
| [getNewIds](m-application-getnewids.md) | Returns a list of IDs of the internal database keys. |
| [getConnection](m-application-getconnection.md) | Returns a new connection to the database server. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Returns a string of characters which is the JSON representation of the list of time differences with UTC time and their start date compared to the UNIX period for a time zone. |
| [onLog](m-application-onlog.md) | Adds or deletes an interception function for the messages written to the journal |
| [onTrace](m-application-ontrace.md) | Adds or deletes a trace message interception function. |

## Properties

| Property | Description |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | Returns the build number of the applicative server. |
| [instanceName](p-application-instancename.md) | Name of the instance where the script is executed. |
| [instanceVarDir](p-application-instancevardir.md) | Complete path of the 'var' directory for the instance where the script is executed. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Full path of the 'upload' directory for the instance where the script is executed. |
| [operator](p-application-operator.md) | Returns an object containing information on the current operator (name, identifiers, rights, etc.). |
| [locale](p-application-locale.md) | Returns a caracter string that matches the instance Local. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
