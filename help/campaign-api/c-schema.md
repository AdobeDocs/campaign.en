# Schema (Class)

Represents schema definition.

A schema is obtained by calling the method of the `application` global variable. An instance of this object has a object as a prototype, and therefore inherits its methods.

## Methods

| Method | Description |
| --- | --- |
| [toDocument](m-schema-todocument.md) | Converts the schema into an XML document form. |

## Properties

| Property | Description |
| --- | --- |
| [enumerations](p-schema-enumerations.md) | Returns the table which contains the list of  [enumerations](c-enumeration.md)  defined in this schema. |
| [id](p-schema-id.md) | The schema identifier in the form of a string. |
| [isLibrary](p-schema-islibrary.md) | Returns a boolean which specified whether the schema is a component library. |
| [labelSingular](p-schema-labelsingular.md) | The singular name of the schema in the form of a string. |
| [mappingType](p-schema-mappingtype.md) | The nature of schema mapping in the form of a string |
| [md5](p-schema-md5.md) | The MD5 code of the schema in the form of a hexadecimal string. |
| [namespace](p-schema-namespace.md) | Namespace of the schema in the form of a string. |
| [root](p-schema-root.md) | Main element of the schema or null if it isn't defined. |
| [userDescription](p-schema-userdescription.md) | The description of the schema in the form of a string. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
