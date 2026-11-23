# BuildPreview

Built the preview of a content to delivery or of a line of the output file (in external mode).

```text
[ XML preview, XML queryResult ] = delivery.BuildPreview ( XML params ) const
```

## Parameters

**params** Recipient filtering condition (@filter = '@id = 5673'), content identifier (@content = 'html', 'text', 'sms', 'webContent1', 'outputFile'...), @targetPart = 1345686...

## Return value(s)

**preview** Returns all the parameters of the generated preview

**queryResult** Returns the data loaded to compute the preview.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

No

**Const:**

Yes

**Key only:**

No
