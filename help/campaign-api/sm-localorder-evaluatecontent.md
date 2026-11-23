# EvaluateContent

Evaluates the content of a delivery linked to an order. This evaluation will be performed when ordering using operator rights and before the local campaign is created.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## Parameters

**order** Element containing order information.

**deliveryId** ID of delivery to evaluate.

**contentType** Type of content to return (html or text for an email; empty string for other channels).

**seedMemberId** Seed address ID used for content personalization.

## Return value(s)

**result** Evaluated content.

## Features

**Schema:** [nms:localOrder](s-nms-localorder.md)

**Static:**

Yes
