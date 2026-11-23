# fileRes

File resource stored on the server or in the database

## Methods

| Method | Description |
| --- | --- |
| [FilePublishing](sm-fileres-filepublishing.md) | Publishes the public resources on the frontal servers. |
| [GetPublicFileResURL](sm-fileres-getpublicfileresurl.md) | Gets the URL of the folder |
| [GetServerFileName](sm-fileres-getserverfilename.md) | Returns the name of the file on the server after copying it, if necessary, in the upload folder. |
| [GetURL](sm-fileres-geturl.md) | Gets the URL of the file |
| [PostUpload](sm-fileres-postupload.md) | Post upload processing depending on defined storage type. |
| [PreDownload](sm-fileres-predownload.md) | Prepare download of resource depending on the defined storage type. |
| [PublishIfNeeded](sm-fileres-publishifneeded.md) | Copies the file on the media servers if necessary |
| [PublishIfNeededFromId](sm-fileres-publishifneededfromid.md) | Copies the file on the media servers if necessary using the resource ID |
| [WebPostUpload](sm-fileres-webpostupload.md) | Finalize the storage of the resource after the upload (from a web page) to the server depending on the storage type used. Recovers the codepage and the content type. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-entity-save.md) | Saves an entity in the database. |
