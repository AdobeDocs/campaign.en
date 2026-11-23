# SchemaNode (Class)

Represents the element of a schema

## Methods

| Method | Description |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | Returns an instance of  [SchemaNode](c-schemanode.md)  or null if the node doesn't exist and the mustExist parameter is set to false. |

## Properties

| Property | Description |
| --- | --- |
| [children](p-schemanode-children.md) | Returns an object for which each property is a child node indexed by its name. |
| [computeString](p-schemanode-computestring.md) | Returns the string calculated by the current node. |
| [dataPolicy](p-schemanode-datapolicy.md) | Returns a string of characters which provides the data policy of the current node. |
| [description](p-schemanode-description.md) | Returns a string of characters describing the current node. |
| [defaultValue](p-schemanode-defaultvalue.md) | Returns a string of characters which provides the default value of the current node. |
| [editType](p-schemanode-edittype.md) | Returns a string of characters which specifies the editing type of the current node. |
| [enumeration](p-schemanode-enumeration.md) | Returns an  [Enumeration](c-enumeration.md)  object which is the enumeration linked to the current node or null if there is no enumeration. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Returns the name of the image of the current node in the form of a string of characters. |
| [folderModel](p-schemanode-foldermodel.md) | Only on the root node, returns a string which contains the folder template(s). On the other nodes, it returns undefined. |
| [image](p-schemanode-image.md) | Returns the name of the image in the form of a string of characters. |
| [integrity](p-schemanode-integrity.md) | Returns the link integrity type. |
| [keys](p-schemanode-keys.md) | Returns a table with definitions of the current node's  [SchemaKey](c-schemakey.md)  keys. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Returns a boolean which indicates whether the value of the current node is linked to an enumeration. |
| [childrenCount](p-schemanode-childrencount.md) | Returns a number which specifies the number of child nodes. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Returns a boolean which indicates whether the current node is linked to an SQL table. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Returns a boolean which indicates whether the value of the current node is linked to a user enumeration. |
| [help](p-schemanode-help.md) | Returns the help character string. |
| [schema](p-schemanode-schema.md) | Returns the instance of this node's parent  [Schema](c-schema.md)  object. |
| [isAdvanced](p-schemanode-isadvanced.md) | Returns a boolean which indicates whether the current node is advanced or not. |
| [isAnyType](p-schemanode-isanytype.md) | Returns a boolean which indicates whether the current node is ordinary. |
| [isAttribute](p-schemanode-isattribute.md) | Returns a boolean which indicates whether the current node is an attribute. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Returns a boolean which indicates whether the value of the current node is incremented automatically. |
| [isAutoPK](p-schemanode-isautopk.md) | Returns a boolean which indicates whether the current node is a primary key. |
| [isBlob](p-schemanode-isblob.md) | Returns a boolean which indicates whether the current node is a BLOB. |
| [isCalculated](p-schemanode-iscalculated.md) | Returns a boolean which indicates whether the value of the current node is the result of a calculation. |
| [isCDATA](p-schemanode-iscdata.md) | Returns a boolean which indicates whether the current node is mapped from CDATA type XML. |
| [isCollection](p-schemanode-iscollection.md) | Returns a boolean which indicates whether the current node is a collection of sub-elements and/or attributes. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Returns a boolean. If the value added is vrai, during record deduplication, the default value (defined in defaultValue) is automatically reapplied during recording. |
| [isElementOnly](p-schemanode-iselementonly.md) | Returns a boolean which indicates whether the current node is a logical sub-division of the schema. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True if the node is a link and if the join is external. |
| [isFeature](p-schemanode-isfeature.md) | Returns a boolean which indicates whether the node is a feature. |
| [isLink](p-schemanode-islink.md) | Returns a boolean which indicates whether the node is a link. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Returns a boolean which indicates whether the node is an XML mapping. |
| [isMemo](p-schemanode-ismemo.md) | Returns a boolean which indicates whether the current node is mapped by a Memo. |
| [isMemoData](p-schemanode-ismemodata.md) | Returns a boolean which indicates whether the current node is mapped by a MemoData. |
| [isNotNull](p-schemanode-isnotnull.md) | Returns a boolean which indicates whether or not the current node can take the null value into account. |
| [isRequired](p-schemanode-isrequired.md) | Returns a boolean which indicates whether or not the value of the current node is mandatory. |
| [isRoot](p-schemanode-isroot.md) | Returns a boolean which indicates whether the node is the root of the schema. |
| [isSQL](p-schemanode-issql.md) | Returns a boolean which indicates whether the current node is mapped in SQL. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Returns a boolean indicating whether the table is a temporary table. The table will not be created during database creation. |
| [isUnbound](p-schemanode-isunbound.md) | Returns a boolean which indicates whether the current node has an unlimited number of children of the same type. |
| [isUser](p-schemanode-isuser.md) | Returns a boolean which indicates whether or not the node is of user-type. |
| [joinParts](p-schemanode-joinparts.md) | Returns a table of SchemaNode instances for which each element represents a condition of the join. |
| [label](p-schemanode-label.md) | Returns a string of characters which is the description of the current node. |
| [name](p-schemanode-name.md) | Returns a string of characters which is the name of the current node. |
| [nodePath](p-schemanode-nodepath.md) | Returns a string of characters which is the absolute path of the current node. |
| [parent](p-schemanode-parent.md) | Returns a  [SchemaNode](c-schemanode.md)  object which is the parent object or null if there isn't one. |
| [PKSequence](p-schemanode-pksequence.md) | Returns a character string that provides the name of the sequence to use for the primary key. |
| [packageStatus](p-schemanode-packagestatus.md) | Returns a number that gives the package status. |
| [reverseLink](p-schemanode-reverselink.md) | If the element is a link, returns a  [SchemaNode](c-schemanode.md)  object which represents a reverse link (via the target schema). If not, the property is not defined. |
| [SQLName](p-schemanode-sqlname.md) | The SQL name of the field. The property is an empty string if the object isn't an SQL type field. |
| [SQLTable](p-schemanode-sqltable.md) | The SQL name of the table. The property is an empty string if the object isn't the main element or if schema mapping isn't of SQL type. |
| [size](p-schemanode-size.md) | The size of the character string type. |
| [tableDefinition](p-schemanode-tabledefinition.md) | An instance of a  [SchemaNode](c-schemanode.md)  which is the description of the table containing the current node, null if there isn't one. |
| [target](p-schemanode-target.md) | The main element of the link target's schema. If the object isn't a link, the property isn't defined. |
| [type](p-schemanode-type.md) | Returns a string of characters which provides the current node's value type. |
| [userEnumeration](p-schemanode-userenumeration.md) | Returns a string of characters which is the name of the user enumeration used by the current node. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
