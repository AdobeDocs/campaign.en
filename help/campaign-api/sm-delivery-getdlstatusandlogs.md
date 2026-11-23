# GetDlStatusAndLogs

Retrieve the last logs from the journal and the delivery status.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Parameters

**deliveryId** Delivery identifier

**lastLogId** Identifier of the last journal entry returned in the previous call

## Return value(s)

**deliveryState** Delivery status

**returnLogs** Log messages

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
