# UpdateBroadLogs

Update the status of the delivery logs, perform error handling and update the delivery counters.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Parameters

**deliveryId** Delivery identifier

**logs** Collection containing the nms:broadLog records to update (@id, @status, @eventDate and @lastModified must be specified)

**deliveryMustExist** Specifies whether to raise an error for an invalid delivery identifier.

## Return value(s)

None.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
