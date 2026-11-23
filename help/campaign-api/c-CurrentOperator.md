# CurrentOperator (Class)

Object containing information on the current operator (name, identifiers, rights, etc.).

This class has a single instance which provides access to certain properties of the applicative server. This singleton is accessible via the property of the `application` global variable.

Example:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Methods

| Method | Description |
| --- | --- |
| [hasRight](m-CurrentOperator-hasRight.md) | Tests if the operator has a specific named right. |

## Properties

| Property | Description |
| --- | --- |
| [login](p-CurrentOperator-login.md) | Returns the login of the current operator. |
| [id](p-CurrentOperator-id.md) | Returns the internal identifier of the current operator. |
| [computeString](p-CurrentOperator-computeString.md) | Returns the current operator description string. By default this is the name of the operator followed by their login. |
| [groups](p-CurrentOperator-groups.md) | Returns the list of identifiers in the current operator groups. |
| [rights](p-CurrentOperator-rights.md) | Returns the list of the current operator's rights. |
| [timezone](p-CurrentOperator-timezone.md) | Returns the name of the time zone used by the current operator. |
| [home](p-CurrentOperator-home.md) | Returns the name of the root folder of the current operator. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
