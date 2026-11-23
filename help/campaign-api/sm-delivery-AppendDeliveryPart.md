# AppendDeliveryPart

Add a part to a delivery being prepared.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Parameters

**deliveryPart** Document representing the delivery part (or a collection of delivery parts).

**retry** Specifies if this is a new try to submit this delivery part.

## Return value(s)

**deliveryPartId** Delivery part identifier in the database (when it is not a collection).

**fatalError** Returns an error code preventing the caller to perform retires. Otherwise, the error can be temporary.

**fatalErrorMsg** Error message associated with the 'fatalError' error code.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
