# StoreMirrorPageInfoEx

Adds information to generate mirror pages for a set of delivery parts.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Parameters

**deliveryId** Delivery identifier

**notification** Is it a notification?

**partsCount** Number of parts

**firstPartId** First part identifier

**notificationId** Notification identifier

## Return value(s)

**fatalError** Returns an error code preventing the caller to perform retires. Otherwise, the error can be temporary.

**fatalErrorMsg** Error message associated with the 'fatalError' error code.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
