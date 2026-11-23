# GetMidBroadLogs

Retrieve the delivery logs modified last in mid-sourcing-mode.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Parameters

**startDate** Retrieve logs modified since this date (on the mid-sourcing server).

**logCount** Maximum number of logs to retrieve, as long as they have not been updated within the same second.

**emitterDate** Reference date from the issuing server. Used to adjust the delivery log dates.

## Return value(s)

**result** Output document, list of delivery logs.

**nextDate** Date of the first log retrieved (greater than startDate).

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
