# DOMNode (Class)

DOMNode is the parent class of different components that make up a document.

## Methods

| Method | Description |
| --- | --- |
| [insertBefore](m-domnode-insertbefore.md) | Insert a node before a specific position. |
| [replaceChild](m-domnode-replacechild.md) | Replace a node. |
| [removeChild](m-domnode-removechild.md) | Delete a node. |
| [appendChild](m-domnode-appendchild.md) | Insert a node at the end of the list of sub-folders. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Tests whether the node has at least one sub-folder. |
| [normalize](m-domnode-normalize.md) | Normalizes the node: adjacent text nodes are merged and empty text nodes are deleted. |
| [hasAttributes](m-domnode-hasattributes.md) | Tests whether the node has at least one attribute. |
| [isSameNode](m-domnode-issamenode.md) | Tests whether the given reference represents the same node. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Tests whether the given namespace is the default. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | Searched the URI of the namespace linked to the given prefix. |
| [isEqualNode](m-domnode-isequalnode.md) | Compares two nodes. |

## Properties

| Property | Description |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | Qualified node name. The name depends on the node type. |
| [nodeValue](p-domnode-nodevalue.md) | Node value. The value depends on the type of node. |
| [nodeType](p-domnode-nodetype.md) | Node type. |
| [parentNode](p-domnode-parentnode.md) | Parent node or null. |
| [childNodes](p-domnode-childnodes.md) | Returns the list of child nodes in the form of a table. |
| [firstChild](p-domnode-firstchild.md) | First child node of this node or null if it has no children. |
| [lastChild](p-domnode-lastchild.md) | Last child node of this node or null if it has no children. |
| [nextSibling](p-domnode-nextsibling.md) | Node following this node or null. |
| [previousSibling](p-domnode-previoussibling.md) | The node immediately preciding this node or null. |
| [attributes](p-domnode-attributes.md) | Returns a table containing the list of attributes if the node is an element, otherwise null. |
| [namespaceURI](p-domnode-namespaceuri.md) | URI of the node namespace. |
| [prefix](p-domnode-prefix.md) | The namespace prefix of this node or empty if not specified. |
| [localName](p-domnode-localname.md) | Local part of the node's qualified name. |
| [baseURI](p-domnode-baseuri.md) | Base URI of this node. |
| [textContent](p-domnode-textcontent.md) | Text content of the node. The value depends on the type of node. |
| [ownerDocument](p-domnode-ownerdocument.md) | The document to which this node belongs. |

## Features

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
