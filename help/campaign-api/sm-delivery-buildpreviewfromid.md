# BuildPreviewFromId

Built the preview of a content to delivery or of a line of the output file (in external mode).

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## Parameters

**deliveryId** Delivery ID.

**params** Recipient filtering condition (@filter = '@id = 5673'), content identifier (@content = 'html', 'text', 'sms', 'webContent1', 'outputFile'...), @targetPart = 1345686...

## Return value(s)

**preview** Returns all the parameters of the generated preview.

**queryResult** Returns the data loaded to compute the preview.

## Example

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
