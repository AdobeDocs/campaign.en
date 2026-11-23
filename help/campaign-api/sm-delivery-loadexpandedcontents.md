# LoadExpandedContents

Load a list of components for preprocessing with dependencies (personalization blocks, options, additional script objects, etc.).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Parameters

**ids** List of component identifiers separated by commas (e.g. 'option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html').

## Return value(s)

**material** Returns the contents as a 'material' element.

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

No

**Const:**

Yes

**Key only:**

No
