# QueueNotification

Request to queue a notification referencing a delivery template.

```text
QueueNotification ( String scenarioName, XML target )
```

## Parameters

**scenarioName** Internal name of the template

**target** Delivery target population

## Return value(s)

None.

## Remarks

This API can only be used in the context of Web applications/Online surveys. Contrary to SubmitNotification, QueueNotification uses a dedicated thread for queued notifications.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
