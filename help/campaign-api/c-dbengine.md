# DBEngine (Class)

Represents a database connection.

This object enables you to query the database and perform related operations.

Most methods in this class require 'sql' rights. If the operator invokes a method and does not have the appropriate rights, an exception is raised. Generally speaking, all methods that change the database require 'sql' rights, while methods which simply view information do not. Refer to the documentation on each method to find out whether or not the rights are required.

## Methods

| Method | Description |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | Deletes the records of a table by packets. |
| [dispose](m-dbengine-dispose.md) | Frees the connection from all resources linked to it. |
| [execute](m-dbengine-execute.md) | Executes a SQL command. |
| [exec](m-dbengine-exec.md) | Alias of the execute command. This function is obsolete, use  [execute()](m-dbengine-execute.md) |
| [query](m-dbengine-query.md) | Executes a SELECT type SQL query. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Executes a SELECT type SQL query with column type specification. |
| [begin](m-dbengine-begin.md) | Starts a new transaction on the connection. |
| [commit](m-dbengine-commit.md) | Approves the transaction in progress on the connection. |
| [rollback](m-dbengine-rollback.md) | Cancels the transaction in progress on the connection. |

## Properties

| Property | Description |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Returns true if the database is Oracle. |
| [isDB2](p-dbengine-isdb2.md) | Returns true if the database is of DB2 type. |
| [isMySQL](p-dbengine-ismysql.md) | Returns true if the database is of MySQL type. |
| [isMSSQL](p-dbengine-ismssql.md) | Returns true if the database is SQL Server. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Returns true if the database is PostgreSQL. |
| [isSybase](p-dbengine-issybase.md) | Returns true if the database is Sybase. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Returns true if the database is Sybase IQ. |
| [isFDA](p-dbengine-isfda.md) | Returns true if the database is accessed through FDA. |
| [isBroken](p-dbengine-isbroken.md) | Returns true if the connection is no longer usable. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Returns true if the database contains unicode data. |
| [useNChar](p-dbengine-usenchar.md) | Returns true if Adobe Campaign uses NCHAR, NVARCHAR, NCLOB, NTEXT type fields. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
