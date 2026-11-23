# DBEngine (Class)

Represents a database connection.

This object enables you to query the database and perform related operations.

Most methods in this class require 'sql' rights. If the operator invokes a method and does not have the appropriate rights, an exception is raised. Generally speaking, all methods that change the database require 'sql' rights, while methods which simply view information do not. Refer to the documentation on each method to find out whether or not the rights are required.

## Methods

| Method | Description |
| --- | --- |
| [batchDelete](m-DBEngine-batchDelete.md) | Deletes the records of a table by packets. |
| [dispose](m-DBEngine-dispose.md) | Frees the connection from all resources linked to it. |
| [execute](m-DBEngine-execute.md) | Executes a SQL command. |
| [exec](m-DBEngine-exec.md) | Alias of the execute command. This function is obsolete, use  [execute()](m-DBEngine-execute.md) |
| [query](m-DBEngine-query.md) | Executes a SELECT type SQL query. |
| [queryWithTypes](m-DBEngine-queryWithTypes.md) | Executes a SELECT type SQL query with column type specification. |
| [begin](m-DBEngine-begin.md) | Starts a new transaction on the connection. |
| [commit](m-DBEngine-commit.md) | Approves the transaction in progress on the connection. |
| [rollback](m-DBEngine-rollback.md) | Cancels the transaction in progress on the connection. |

## Properties

| Property | Description |
| --- | --- |
| [isOracle](p-DBEngine-isOracle.md) | Returns true if the database is Oracle. |
| [isDB2](p-DBEngine-isDB2.md) | Returns true if the database is of DB2 type. |
| [isMySQL](p-DBEngine-isMySQL.md) | Returns true if the database is of MySQL type. |
| [isMSSQL](p-DBEngine-isMSSQL.md) | Returns true if the database is SQL Server. |
| [isPostgreSQL](p-DBEngine-isPostgreSQL.md) | Returns true if the database is PostgreSQL. |
| [isSybase](p-DBEngine-isSybase.md) | Returns true if the database is Sybase. |
| [isSybaseIQ](p-DBEngine-isSybaseIQ.md) | Returns true if the database is Sybase IQ. |
| [isFDA](p-DBEngine-isFDA.md) | Returns true if the database is accessed through FDA. |
| [isBroken](p-DBEngine-isBroken.md) | Returns true if the connection is no longer usable. |
| [useUnicodeData](p-DBEngine-useUnicodeData.md) | Returns true if the database contains unicode data. |
| [useNChar](p-DBEngine-useNChar.md) | Returns true if Adobe Campaign uses NCHAR, NVARCHAR, NCLOB, NTEXT type fields. |

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
