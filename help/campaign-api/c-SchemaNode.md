# SchemaNode (Class)

Represents the element of a schema

## Methods

| Method | Description |
| --- | --- |
| [findNode](m-SchemaNode-findNode.md) | Returns an instance of  [SchemaNode](c-SchemaNode.md)  or null if the node doesn't exist and the mustExist parameter is set to false. |

## Properties

| Property | Description |
| --- | --- |
| [children](p-SchemaNode-children.md) | Returns an object for which each property is a child node indexed by its name. |
| [computeString](p-SchemaNode-computeString.md) | Returns the string calculated by the current node. |
| [dataPolicy](p-SchemaNode-dataPolicy.md) | Returns a string of characters which provides the data policy of the current node. |
| [description](p-SchemaNode-description.md) | Returns a string of characters describing the current node. |
| [defaultValue](p-SchemaNode-defaultValue.md) | Returns a string of characters which provides the default value of the current node. |
| [editType](p-SchemaNode-editType.md) | Returns a string of characters which specifies the editing type of the current node. |
| [enumeration](p-SchemaNode-enumeration.md) | Returns an  [Enumeration](c-Enumeration.md)  object which is the enumeration linked to the current node or null if there is no enumeration. |
| [enumerationImage](p-SchemaNode-enumerationImage.md) | Returns the name of the image of the current node in the form of a string of characters. |
| [folderModel](p-SchemaNode-folderModel.md) | Only on the root node, returns a string which contains the folder template(s). On the other nodes, it returns undefined. |
| [image](p-SchemaNode-image.md) | Returns the name of the image in the form of a string of characters. |
| [integrity](p-SchemaNode-integrity.md) | Returns the link integrity type. |
| [keys](p-SchemaNode-keys.md) | Returns a table with definitions of the current node's  [SchemaKey](c-SchemaKey.md)  keys. |
| [hasEnumeration](p-SchemaNode-hasEnumeration.md) | Returns a boolean which indicates whether the value of the current node is linked to an enumeration. |
| [childrenCount](p-SchemaNode-childrenCount.md) | Returns a number which specifies the number of child nodes. |
| [hasSQLTable](p-SchemaNode-hasSQLTable.md) | Returns a boolean which indicates whether the current node is linked to an SQL table. |
| [hasUserEnumeration](p-SchemaNode-hasUserEnumeration.md) | Returns a boolean which indicates whether the value of the current node is linked to a user enumeration. |
| [help](p-SchemaNode-help.md) | Returns the help character string. |
| [schema](p-SchemaNode-schema.md) | Returns the instance of this node's parent  [Schema](c-Schema.md)  object. |
| [isAdvanced](p-SchemaNode-isAdvanced.md) | Returns a boolean which indicates whether the current node is advanced or not. |
| [isAnyType](p-SchemaNode-isAnyType.md) | Returns a boolean which indicates whether the current node is ordinary. |
| [isAttribute](p-SchemaNode-isAttribute.md) | Returns a boolean which indicates whether the current node is an attribute. |
| [isAutoIncrement](p-SchemaNode-isAutoIncrement.md) | Returns a boolean which indicates whether the value of the current node is incremented automatically. |
| [isAutoPK](p-SchemaNode-isAutoPK.md) | Returns a boolean which indicates whether the current node is a primary key. |
| [isBlob](p-SchemaNode-isBlob.md) | Returns a boolean which indicates whether the current node is a BLOB. |
| [isCalculated](p-SchemaNode-isCalculated.md) | Returns a boolean which indicates whether the value of the current node is the result of a calculation. |
| [isCDATA](p-SchemaNode-isCDATA.md) | Returns a boolean which indicates whether the current node is mapped from CDATA type XML. |
| [isCollection](p-SchemaNode-isCollection.md) | Returns a boolean which indicates whether the current node is a collection of sub-elements and/or attributes. |
| [isDefaultOnDuplicate](p-SchemaNode-isDefaultOnDuplicate.md) | Returns a boolean. If the value added is vrai, during record deduplication, the default value (defined in defaultValue) is automatically reapplied during recording. |
| [isElementOnly](p-SchemaNode-isElementOnly.md) | Returns a boolean which indicates whether the current node is a logical sub-division of the schema. |
| [isExternalJoin](p-SchemaNode-isExternalJoin.md) | True if the node is a link and if the join is external. |
| [isFeature](p-SchemaNode-isFeature.md) | Returns a boolean which indicates whether the node is a feature. |
| [isLink](p-SchemaNode-isLink.md) | Returns a boolean which indicates whether the node is a link. |
| [isMappedAsXML](p-SchemaNode-isMappedAsXML.md) | Returns a boolean which indicates whether the node is an XML mapping. |
| [isMemo](p-SchemaNode-isMemo.md) | Returns a boolean which indicates whether the current node is mapped by a Memo. |
| [isMemoData](p-SchemaNode-isMemoData.md) | Returns a boolean which indicates whether the current node is mapped by a MemoData. |
| [isNotNull](p-SchemaNode-isNotNull.md) | Returns a boolean which indicates whether or not the current node can take the null value into account. |
| [isRequired](p-SchemaNode-isRequired.md) | Returns a boolean which indicates whether or not the value of the current node is mandatory. |
| [isRoot](p-SchemaNode-isRoot.md) | Returns a boolean which indicates whether the node is the root of the schema. |
| [isSQL](p-SchemaNode-isSQL.md) | Returns a boolean which indicates whether the current node is mapped in SQL. |
| [isTemporaryTable](p-SchemaNode-isTemporaryTable.md) | Returns a boolean indicating whether the table is a temporary table. The table will not be created during database creation. |
| [isUnbound](p-SchemaNode-isUnbound.md) | Returns a boolean which indicates whether the current node has an unlimited number of children of the same type. |
| [isUser](p-SchemaNode-isUser.md) | Returns a boolean which indicates whether or not the node is of user-type. |
| [joinParts](p-SchemaNode-joinParts.md) | Returns a table of SchemaNode instances for which each element represents a condition of the join. |
| [label](p-SchemaNode-label.md) | Returns a string of characters which is the description of the current node. |
| [name](p-SchemaNode-name.md) | Returns a string of characters which is the name of the current node. |
| [nodePath](p-SchemaNode-nodePath.md) | Returns a string of characters which is the absolute path of the current node. |
| [parent](p-SchemaNode-parent.md) | Returns a  [SchemaNode](c-SchemaNode.md)  object which is the parent object or null if there isn't one. |
| [PKSequence](p-SchemaNode-PKSequence.md) | Returns a character string that provides the name of the sequence to use for the primary key. |
| [packageStatus](p-SchemaNode-packageStatus.md) | Returns a number that gives the package status. |
| [reverseLink](p-SchemaNode-reverseLink.md) | If the element is a link, returns a  [SchemaNode](c-SchemaNode.md)  object which represents a reverse link (via the target schema). If not, the property is not defined. |
| [SQLName](p-SchemaNode-SQLName.md) | The SQL name of the field. The property is an empty string if the object isn't an SQL type field. |
| [SQLTable](p-SchemaNode-SQLTable.md) | The SQL name of the table. The property is an empty string if the object isn't the main element or if schema mapping isn't of SQL type. |
| [size](p-SchemaNode-size.md) | The size of the character string type. |
| [tableDefinition](p-SchemaNode-tableDefinition.md) | An instance of a  [SchemaNode](c-SchemaNode.md)  which is the description of the table containing the current node, null if there isn't one. |
| [target](p-SchemaNode-target.md) | The main element of the link target's schema. If the object isn't a link, the property isn't defined. |
| [type](p-SchemaNode-type.md) | Returns a string of characters which provides the current node's value type. |
| [userEnumeration](p-SchemaNode-userEnumeration.md) | Returns a string of characters which is the name of the user enumeration used by the current node. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
