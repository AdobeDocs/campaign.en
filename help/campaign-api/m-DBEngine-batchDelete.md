# batchDelete

Deletes the records of a table by packets.

```text
batchDelete (table, pk [, where ])
```

## Parameters

**table** SQL name of the table.

**pk** Field name used as primary key.

**where** SQL record-filtering condition.

## Return value

None.

## Remarks

Example:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

The operator needs 'sql' rights to use this function, otherwise an exception is raised.

## Features

**Method of class:** [DBEngine](c-DBEngine.md)

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
