# GetQuarantines

Retrieves the latest quarantines and quarantine exits.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Parameters

**startDate** Retrieve the quarantines modified since this date. When empty, the pointer value is used.

**pointerName** Retrieve the quarantines modified since this pointer (optional).

**quarantineCount** Maximum number of quarantines to retrieve, provided they were not updated during the same second.

**callerDate** Caller reference date. Lets you modify the quarantine date referential (optional).

## Return value(s)

**result** Output document, list of quarantines.

**nextDate** Date of the first non-retrieved quarantine (strictly higher than startDate).

**hasMore** If so, there are still quarantines to retrieve.

## Features

**Schema:** [nms:address](s-nms-address.md)

**Static:**

Yes
