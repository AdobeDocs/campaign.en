# TestCalcField

Test the calculated field using the sample lines stored in the script.

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Parameters

**dataTransferStep** Data transfer step where the calculated field is defined

**calcFieldName** Calculated field to test

## Return value(s)

**calcFieldValues** Returns the list of values for each sample line (calcFieldValues/line) and the field name (calcFieldValues/@name)

## Features

**Schema:** [xtk:dataTransfer](s-xtk-dataTransfer.md)

**Static:**

Yes
