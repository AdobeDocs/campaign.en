# ExportPreview

Compute output file column preview for the first lines of the query

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Parameters

**dataTransferStep** Transfer step where the calculated field is defined.

**lineCount** Number of lines to return

**countMode** Line counting mode

**calcFieldName** Name of the observed calculated field. If empty, it is a global preview of the output file.

## Return value(s)

**resultColumns** Returns the values of the export file columns (line/col/val, line/col/errors).

**resultXML** Returns the output XML document of the query.

**resultSQLRequest** Returns the SQL query executed.

## Features

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Static:**

Yes
