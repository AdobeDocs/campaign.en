# EvaluateTargetFromId

Evaluates campaign targeting for each campaign delivery linked to an order. This evaluation will be performed when ordering using operator rights and before the local campaign is created.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Parameters

**orderId** Order ID.

## Return value(s)

**result** Result of counts for each of the campaign deliveries.

## Features

**Schema:** [nms:localOrder](s-nms-localOrder.md)

**Static:**

Yes
