# DOMNode (Class)

DOMNode is the parent class of different components that make up a document.

## Methods

| Method | Description |
| --- | --- |
| [insertBefore](m-DOMNode-insertBefore.md) | Insert a node before a specific position. |
| [replaceChild](m-DOMNode-replaceChild.md) | Replace a node. |
| [removeChild](m-DOMNode-removeChild.md) | Delete a node. |
| [appendChild](m-DOMNode-appendChild.md) | Insert a node at the end of the list of sub-folders. |
| [hasChildNodes](m-DOMNode-hasChildNodes.md) | Tests whether the node has at least one sub-folder. |
| [normalize](m-DOMNode-normalize.md) | Normalizes the node: adjacent text nodes are merged and empty text nodes are deleted. |
| [hasAttributes](m-DOMNode-hasAttributes.md) | Tests whether the node has at least one attribute. |
| [isSameNode](m-DOMNode-isSameNode.md) | Tests whether the given reference represents the same node. |
| [isDefaultNamespace](m-DOMNode-isDefaultNamespace.md) | Tests whether the given namespace is the default. |
| [lookupNamespaceURI](m-DOMNode-lookupNamespaceURI.md) | Searched the URI of the namespace linked to the given prefix. |
| [isEqualNode](m-DOMNode-isEqualNode.md) | Compares two nodes. |

## Properties

| Property | Description |
| --- | --- |
| [nodeName](p-DOMNode-nodeName.md) | Qualified node name. The name depends on the node type. |
| [nodeValue](p-DOMNode-nodeValue.md) | Node value. The value depends on the type of node. |
| [nodeType](p-DOMNode-nodeType.md) | Node type. |
| [parentNode](p-DOMNode-parentNode.md) | Parent node or null. |
| [childNodes](p-DOMNode-childNodes.md) | Returns the list of child nodes in the form of a table. |
| [firstChild](p-DOMNode-firstChild.md) | First child node of this node or null if it has no children. |
| [lastChild](p-DOMNode-lastChild.md) | Last child node of this node or null if it has no children. |
| [nextSibling](p-DOMNode-nextSibling.md) | Node following this node or null. |
| [previousSibling](p-DOMNode-previousSibling.md) | The node immediately preciding this node or null. |
| [attributes](p-DOMNode-attributes.md) | Returns a table containing the list of attributes if the node is an element, otherwise null. |
| [namespaceURI](p-DOMNode-namespaceURI.md) | URI of the node namespace. |
| [prefix](p-DOMNode-prefix.md) | The namespace prefix of this node or empty if not specified. |
| [localName](p-DOMNode-localName.md) | Local part of the node's qualified name. |
| [baseURI](p-DOMNode-baseURI.md) | Base URI of this node. |
| [textContent](p-DOMNode-textContent.md) | Text content of the node. The value depends on the type of node. |
| [ownerDocument](p-DOMNode-ownerDocument.md) | The document to which this node belongs. |

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
