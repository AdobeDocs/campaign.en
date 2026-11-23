# session

Sessions to the application server

## Methods

| Method | Description |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | Applies the duplication settings (including default values) to the specified document |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | connection token |
| [ChangePassword](sm-session-changepassword.md) | Change current password |
| [DeleteCollection](sm-session-deletecollection.md) | Delete a list of entities based on a condition |
| [Diff](sm-session-diff.md) | Returns the current version and the original version of a document. |
| [Duplicate](sm-session-duplicate.md) | Creates a new document from a source document |
| [DuplicateTo](sm-session-duplicateto.md) | Duplicates a new document from a source document to a given folder |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Duplicates a new document from the source document with the ID mapping |
| [Encrypt](sm-session-encrypt.md) | Encrypts the character string with the instance key. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | Encrypts the character string with the server key. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Applies a transformation to the character string according to the data policy passed as a parameter. Leaves the string unchanged in case of failure. |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | Returns a document containing the menus of the applications enabled for the current login |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Recovers information from the current connections. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Returns a document containing an empty entity with its default values |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Return dirty cached entities |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Load an entity if its MD5 key is different than the one given as a parameter |
| [GetImages](sm-session-getimages.md) | Load a list of images |
| [GetNewIds](sm-session-getnewids.md) | Gathers a list of internal keys identifiers for the database. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Get a list of unique identifiers from the database, given a sequence name. |
| [GetOption](sm-session-getoption.md) | Returns the value of an option stored in the database. |
| [GetPkList](sm-session-getpklist.md) | Get the list of instance identifiers |
| [GetServerTime](sm-session-getservertime.md) | Returns the server date and time |
| [GetUserInfo](sm-session-getuserinfo.md) | Information about current operator |
| [HashPassword](sm-session-hashpassword.md) | Hash a password with the server key. |
| [ImportCollection](sm-session-importcollection.md) | Update a list of entities using an import |
| [KillSession](sm-session-killsession.md) | Closes the session specified |
| [Load](sm-session-load.md) | Load the entity |
| [LoadAsText](sm-session-loadastext.md) | Retrieve entity contents as text |
| [LoadIfExists](sm-session-loadifexists.md) | Load the entity if it exists |
| [Logoff](sm-session-logoff.md) | Close current session |
| [Logon](sm-session-logon.md) | Opens a session |
| [NewInstance](sm-session-newinstance.md) | New document creation, pre-initialized but not saved |
| [Remove](sm-session-remove.md) | Delete entity |
| [ServerShutdown](sm-session-servershutdown.md) | Requests server shutdown |
| [SetDefaultValues](sm-session-setdefaultvalues.md) | Fix values by default based on xpath |
| [SetDefaults](sm-session-setdefaults.md) | Set default values |
| [TestCnx](sm-session-testcnx.md) | Test the connection. |
| [Write](sm-session-write.md) | Update an entity |
| [WriteCollection](sm-session-writecollection.md) | Update a list of entities |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-entity-save.md) | Saves an entity in the database. |
