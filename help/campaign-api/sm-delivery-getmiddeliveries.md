# GetMidDeliveries

Retrieve the status of the deliveries modified last in mid-sourcing-mode.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Parameters

**startDate** Retrieve modifications since this date (on the mid-sourcing server).

**maxCount** Maximum number of deliveries to retrieve, provided they were not updated during the same second.

**emitterDate** Reference date of the issuing server. Used to adjust dates of deliveries.

## Return value(s)

**result** Output document, list of deliveries updated.

**nextDate** Start date for the next call.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
