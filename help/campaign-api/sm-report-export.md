# Export

Generating and exporting a report

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Parameters

**reportName** Internal name of the report

**context** Execution context.

**exportFormat** Possible values are : XLS, OOXML\_SS, ODF\_SS, PDF

XLS generates an Excel 94-2003 document\
 OOXML\_SS generates an Excel 2007 document\
 ODF\_SS generates an Open document

**fileName** Output file name

**isAdHoc** Specifies whether the export concerns an ad hoc report

## Return value(s)

None.

## Features

**Schema:** [xtk:report](s-xtk-report.md)

**Static:**

Yes
