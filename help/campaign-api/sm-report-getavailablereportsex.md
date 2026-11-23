# GetAvailableReportsEx

Recovers the list of reports without their history, taking data sorting conditions and page numbering into account

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Parameters

**activeContext** Active context (selection, global)

**schema** Schema involved

**selection** IDs of the selected entities, separated by ','

**where** Filtering 'where' node

**orderBy** Sorting 'orderBy' node

**editionMode** During editing, non-published reports are also visible

**lineCount** Number of reports to collect

**startLine** Offset to apply for page numbering

**locationName**

## Return value(s)

**reports** List of eligible reports

## Features

**Schema:** [xtk:report](s-xtk-report.md)

**Static:**

Yes
