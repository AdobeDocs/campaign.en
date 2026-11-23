# DeployTriggerMessageSingle

Publish the transactional message on execution instances. Returns true if the publication is successful and false if not.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Parameters

**deliveryId** ID of the delivery to deploy

**localPublish** Publish on the control instance only?

## Return value(s)

**isSuccess** Publication complete

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
