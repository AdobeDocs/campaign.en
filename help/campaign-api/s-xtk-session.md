# session

Sessions to the application server

## Methods

| Method | Description |
| --- | --- |
| [ApplyDuplicateRules](sm-session-ApplyDuplicateRules.md) | Applies the duplication settings (including default values) to the specified document |
| [BearerTokenLogon](sm-session-BearerTokenLogon.md) | connection token |
| [ChangePassword](sm-session-ChangePassword.md) | Change current password |
| [DeleteCollection](sm-session-DeleteCollection.md) | Delete a list of entities based on a condition |
| [Diff](sm-session-Diff.md) | Returns the current version and the original version of a document. |
| [Duplicate](sm-session-Duplicate.md) | Creates a new document from a source document |
| [DuplicateTo](sm-session-DuplicateTo.md) | Duplicates a new document from a source document to a given folder |
| [DuplicateWithMappingId](sm-session-DuplicateWithMappingId.md) | Duplicates a new document from the source document with the ID mapping |
| [Encrypt](sm-session-Encrypt.md) | Encrypts the character string with the instance key. |
| [EncryptServerPassword](sm-session-EncryptServerPassword.md) | Encrypts the character string with the server key. |
| [FormatDataPolicy](sm-session-FormatDataPolicy.md) | Applies a transformation to the character string according to the data policy passed as a parameter. Leaves the string unchanged in case of failure. |
| [GetActiveApplicationMenus](sm-session-GetActiveApplicationMenus.md) | Returns a document containing the menus of the applications enabled for the current login |
| [GetCnxInfo](sm-session-GetCnxInfo.md) | Recovers information from the current connections. |
| [GetDefaultEntity](sm-session-GetDefaultEntity.md) | Returns a document containing an empty entity with its default values |
| [GetDirtyCacheEntities](sm-session-GetDirtyCacheEntities.md) | Return dirty cached entities |
| [GetEntityIfMoreRecent](sm-session-GetEntityIfMoreRecent.md) | Load an entity if its MD5 key is different than the one given as a parameter |
| [GetImages](sm-session-GetImages.md) | Load a list of images |
| [GetNewIds](sm-session-GetNewIds.md) | Gathers a list of internal keys identifiers for the database. |
| [GetNewIdsEx](sm-session-GetNewIdsEx.md) | Get a list of unique identifiers from the database, given a sequence name. |
| [GetOption](sm-session-GetOption.md) | Returns the value of an option stored in the database. |
| [GetPkList](sm-session-GetPkList.md) | Get the list of instance identifiers |
| [GetServerTime](sm-session-GetServerTime.md) | Returns the server date and time |
| [GetUserInfo](sm-session-GetUserInfo.md) | Information about current operator |
| [HashPassword](sm-session-HashPassword.md) | Hash a password with the server key. |
| [ImportCollection](sm-session-ImportCollection.md) | Update a list of entities using an import |
| [KillSession](sm-session-KillSession.md) | Closes the session specified |
| [Load](sm-session-Load.md) | Load the entity |
| [LoadAsText](sm-session-LoadAsText.md) | Retrieve entity contents as text |
| [LoadIfExists](sm-session-LoadIfExists.md) | Load the entity if it exists |
| [Logoff](sm-session-Logoff.md) | Close current session |
| [Logon](sm-session-Logon.md) | Opens a session |
| [NewInstance](sm-session-NewInstance.md) | New document creation, pre-initialized but not saved |
| [Remove](sm-session-Remove.md) | Delete entity |
| [ServerShutdown](sm-session-ServerShutdown.md) | Requests server shutdown |
| [SetDefaultValues](sm-session-SetDefaultValues.md) | Fix values by default based on xpath |
| [SetDefaults](sm-session-SetDefaults.md) | Set default values |
| [TestCnx](sm-session-TestCnx.md) | Test the connection. |
| [Write](sm-session-Write.md) | Update an entity |
| [WriteCollection](sm-session-WriteCollection.md) | Update a list of entities |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
