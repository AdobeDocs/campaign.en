# builder

Generation services of the application server

## Methods

| Method | Description |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | Merge the navigation tree definitions found in the database with the one given in parameter. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Generates a schema from a source schema. |
| [BuildSchema](sm-builder-buildschema.md) | Generates a schema from a source schema. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | Generates a schema from a source schema identifier. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Generates a document describing differences between the actual database structure and its logical description. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Generates a document describing the differences between a table in the physical database and the logical description of this table. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Generates a document describing differences between the actual database structure and its logical description. |
| [CheckTableExists](sm-builder-checktableexists.md) | Verifies whether a table exists in the database |
| [CreateDb](sm-builder-createdb.md) | Create database |
| [EvaluateJavaScript](sm-builder-evaluatejavascript.md) | Evaluation of JavaScript code. |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | JavaScript template (JST) evaluation. |
| [ExecSql](sm-builder-execsql.md) | Execute a SQL statement |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Execute a SQL script |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Generates the SQL script used to create the database structure. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Generates the SQL script used to create or update autoPk schema sequence |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Merge all the navigation tree definitions and save the result as 'xtk:merged'. |
| [GenerateSchema](sm-builder-generateschema.md) | Generate the schema code using high-level parameters. |
| [GetDbParams](sm-builder-getdbparams.md) | Retrieves current parameters of datasource. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Retrieve the default namespace. |
| [InstallPackage](sm-builder-installpackage.md) | Install a package. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Installing a package (internal method, do not use). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Install one or more standard packages. |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | Removes the schema and reverse links referencing it. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Solves dependencies in the package |
| [UpdateDb](sm-builder-updatedb.md) | Database structure update. |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | Update the schema based on its physical representation in the database. |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | Updates a collection of schemas based on their physical representation in the database. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-entity-save.md) | Saves an entity in the database. |
