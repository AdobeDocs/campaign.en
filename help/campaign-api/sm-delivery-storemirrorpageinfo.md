# StoreMirrorPageInfo

Adds information to generate mirror pages for a set of delivery parts.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Parameters

**deliveryId** Delivery identifier

**partsCount** Number of parts

**firstPartId** First part identifier

**lastPartId** Last part identifier

## Return value(s)

**fatalError** Returns an error code preventing the caller to perform retires. Otherwise, the error can be temporary.

**fatalErrorMsg** Error message associated with the 'fatalError' error code.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
