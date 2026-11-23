# ExecCommand

Execute a command on a delivery.

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## Parameters

**deliveryId** Delivery identifier

**command** Command name ('play', 'pause' or 'stop')

## Return value(s)

**newState** Delivery status after the command is executed

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
