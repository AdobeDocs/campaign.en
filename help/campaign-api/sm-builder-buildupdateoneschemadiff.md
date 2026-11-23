# BuildUpdateOneSchemaDiff

Generates a document describing the differences between a table in the physical database and the logical description of this table.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Parameters

**schemaId** Schema identifier

**useNamingConventions** Use SQL naming conventions to compute paths of new fields.

## Return value(s)

**sqlSchemaDiff** Generated schema

## Features

**Schema:** [xtk:builder](s-xtk-builder.md)

**Static:**

Yes
