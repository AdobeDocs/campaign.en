# DeclareTableSpaces

Declares the options, required for using specific tablespaces in the remote database accessible via the external account, in the Adobe Campaign database.

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## Parameters

**extAccountId** Internal name or primary key of the external Account

**tableSpace** Name of the tablespace to use for remote work tables

**tableSpaceIndex** Name of the tablespace to use for indexes

## Return value(s)

None.

## Features

**Schema:** [nms:extAccount](s-nms-extAccount.md)

**Static:**

Yes
