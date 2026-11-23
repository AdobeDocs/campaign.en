# builder

Generation services of the application server

## Methods

| Method | Description |
| --- | --- |
| [BuildOutputNavTree](sm-builder-BuildOutputNavTree.md) | Merge the navigation tree definitions found in the database with the one given in parameter. |
| [BuildOutputSchema](sm-builder-BuildOutputSchema.md) | Generates a schema from a source schema. |
| [BuildSchema](sm-builder-BuildSchema.md) | Generates a schema from a source schema. |
| [BuildSchemaFromId](sm-builder-BuildSchemaFromId.md) | Generates a schema from a source schema identifier. |
| [BuildSqlSchemaDiff](sm-builder-BuildSqlSchemaDiff.md) | Generates a document describing differences between the actual database structure and its logical description. |
| [BuildUpdateOneSchemaDiff](sm-builder-BuildUpdateOneSchemaDiff.md) | Generates a document describing the differences between a table in the physical database and the logical description of this table. |
| [BuildUpdateSchemaDiff](sm-builder-BuildUpdateSchemaDiff.md) | Generates a document describing differences between the actual database structure and its logical description. |
| [CheckTableExists](sm-builder-CheckTableExists.md) | Verifies whether a table exists in the database |
| [CreateDb](sm-builder-CreateDb.md) | Create database |
| [EvaluateJavaScript](sm-builder-EvaluateJavaScript.md) | Evaluation of JavaScript code. |
| [EvaluateJavaScriptTemplate](sm-builder-EvaluateJavaScriptTemplate.md) | JavaScript template (JST) evaluation. |
| [ExecSql](sm-builder-ExecSql.md) | Execute a SQL statement |
| [ExecSqlScript](sm-builder-ExecSqlScript.md) | Execute a SQL script |
| [GenCreateDbDDL](sm-builder-GenCreateDbDDL.md) | Generates the SQL script used to create the database structure. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-GenCreateOrUpdateSchemaSequenceDDL.md) | Generates the SQL script used to create or update autoPk schema sequence |
| [GenerateNavTree](sm-builder-GenerateNavTree.md) | Merge all the navigation tree definitions and save the result as 'xtk:merged'. |
| [GenerateSchema](sm-builder-GenerateSchema.md) | Generate the schema code using high-level parameters. |
| [GetDbParams](sm-builder-GetDbParams.md) | Retrieves current parameters of datasource. |
| [GetDefaultNamespace](sm-builder-GetDefaultNamespace.md) | Retrieve the default namespace. |
| [InstallPackage](sm-builder-InstallPackage.md) | Install a package. |
| [InstallPackageImpl](sm-builder-InstallPackageImpl.md) | Installing a package (internal method, do not use). |
| [InstallVendorPackages](sm-builder-InstallVendorPackages.md) | Install one or more standard packages. |
| [RemoveSchemaLinkRef](sm-builder-RemoveSchemaLinkRef.md) | Removes the schema and reverse links referencing it. |
| [ResolvePackageReferences](sm-builder-ResolvePackageReferences.md) | Solves dependencies in the package |
| [UpdateDb](sm-builder-UpdateDb.md) | Database structure update. |
| [UpdateSchemaFromDatabase](sm-builder-UpdateSchemaFromDatabase.md) | Update the schema based on its physical representation in the database. |
| [UpdateTempSchemasFromDatabase](sm-builder-UpdateTempSchemasFromDatabase.md) | Updates a collection of schemas based on their physical representation in the database. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
