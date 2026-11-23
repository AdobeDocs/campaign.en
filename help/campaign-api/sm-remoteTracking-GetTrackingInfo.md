# GetTrackingInfo

Allows a remote redirection server to download information about a delivery action.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Parameters

**instance** Instance name

**dbId** Database identifier for customer performing a delivery

**deliveryId** Delivery ID.

## Return value(s)

**document** Document containing the tracking information for this delivery

## Features

**Schema:** [nms:remoteTracking](s-nms-remoteTracking.md)

**Static:**

Yes
