# SubmitMidSourcing

Submit a delivery in mid-sourcing mode.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Parameters

**delivery** Document representing the delivery.

**routingMatch** No longer used

**folderName** Full folder name (in the sender database).

## Return value(s)

**remoteId** Identifier of the delivery in the receiver database.

**remoteMatchId** No longer used

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
