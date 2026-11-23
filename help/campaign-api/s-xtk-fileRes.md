# fileRes

File resource stored on the server or in the database

## Methods

| Method | Description |
| --- | --- |
| [FilePublishing](sm-fileRes-FilePublishing.md) | Publishes the public resources on the frontal servers. |
| [GetPublicFileResURL](sm-fileRes-GetPublicFileResURL.md) | Gets the URL of the folder |
| [GetServerFileName](sm-fileRes-GetServerFileName.md) | Returns the name of the file on the server after copying it, if necessary, in the upload folder. |
| [GetURL](sm-fileRes-GetURL.md) | Gets the URL of the file |
| [PostUpload](sm-fileRes-PostUpload.md) | Post upload processing depending on defined storage type. |
| [PreDownload](sm-fileRes-PreDownload.md) | Prepare download of resource depending on the defined storage type. |
| [PublishIfNeeded](sm-fileRes-PublishIfNeeded.md) | Copies the file on the media servers if necessary |
| [PublishIfNeededFromId](sm-fileRes-PublishIfNeededFromId.md) | Copies the file on the media servers if necessary using the resource ID |
| [WebPostUpload](sm-fileRes-WebPostUpload.md) | Finalize the storage of the resource after the upload (from a web page) to the server depending on the storage type used. Recovers the codepage and the content type. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
