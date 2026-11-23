# EvaluateTarget

Evaluates campaign targeting for each campaign delivery linked to an order. This evaluation will be performed when ordering using operator rights and before the local campaign is created.

```text
XML result = EvaluateTarget ( XML order )
```

## Parameters

**order** Element containing order information.

## Return value(s)

**result** Result of counts for each of the campaign deliveries.

## Features

**Schema:** [nms:localOrder](s-nms-localOrder.md)

**Static:**

Yes
