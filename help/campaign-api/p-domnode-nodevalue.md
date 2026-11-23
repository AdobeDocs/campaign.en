# nodeValue

Node value. The value depends on the type of node.

```text
nodeValue
```

## Remarks

This property can be accessed with read and write permissions. Example to retrieve a subject line and add it to the additionnal data from a query activity in a workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Example to retrieve a subject line from an enrichment activity in a workflow:

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Features

**Property of class:** [DOMNode](c-domnode.md)

**Read only:**

Yes

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
