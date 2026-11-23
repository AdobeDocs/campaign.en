# Application (Class)

This class has a single instance which provides access to certain properties of the applicative server. This singleton is accessible via the `application` global variable.

## Methods

| Method | Description |
| --- | --- |
| [hasPackage](m-Application-hasPackage.md) | Tests if a package is installed. |
| [getSchema](m-Application-getSchema.md) | Returns a mapping to an Adobe Campaign schema or null if the schema doesn't exist. |
| [getDBMSType](m-Application-getDBMSType.md) | Returns the server type of the database. |
| [getNewIds](m-Application-getNewIds.md) | Returns a list of IDs of the internal database keys. |
| [getConnection](m-Application-getConnection.md) | Returns a new connection to the database server. |
| [getTimezoneJson](m-Application-getTimezoneJson.md) | Returns a string of characters which is the JSON representation of the list of time differences with UTC time and their start date compared to the UNIX period for a time zone. |
| [onLog](m-Application-onLog.md) | Adds or deletes an interception function for the messages written to the journal |
| [onTrace](m-Application-onTrace.md) | Adds or deletes a trace message interception function. |

## Properties

| Property | Description |
| --- | --- |
| [buildNumber](p-Application-buildNumber.md) | Returns the build number of the applicative server. |
| [instanceName](p-Application-instanceName.md) | Name of the instance where the script is executed. |
| [instanceVarDir](p-Application-instanceVarDir.md) | Complete path of the 'var' directory for the instance where the script is executed. |
| [instanceUploadDir](p-Application-instanceUploadDir.md) | Full path of the 'upload' directory for the instance where the script is executed. |
| [operator](p-Application-operator.md) | Returns an object containing information on the current operator (name, identifiers, rights, etc.). |
| [locale](p-Application-locale.md) | Returns a caracter string that matches the instance Local. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
