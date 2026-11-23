# FinalizeMidPreparation

Finalize the analysis of a delivery in mid-sourcing mode.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Parameters

**deliveryId** Delivery identifier

**errorCode** Error code returned by the analysis on the marketing database (method-level error code is not used for this)

**properties** Delivery properties to update

**retry** Specifies if this is a retry for the method call.

## Return value(s)

**fatalError** Returns an error code preventing the caller to perform retires. Otherwise, the error can be temporary.

**fatalErrorMsg** Error message associated with the 'fatalError' error code.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
