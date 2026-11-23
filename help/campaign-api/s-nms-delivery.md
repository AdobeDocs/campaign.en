# delivery

This schema represents a delivery action or template.

A template is a delivery template including all the necessary parameters. A delivery template can be executed manually from the client console, or executed when an event occurs (started from the scheduler, or programmatically from an SOAP call).

## Methods

| Method | Description |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Add a part to a delivery being prepared. |
| [BuildForward](sm-delivery-buildforward.md) | Builds the HTML page. |
| [BuildMirror](sm-delivery-buildmirror.md) | Build the HTML mirror page. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Build the HTML mirror page. |
| [BuildPreview](sm-delivery-buildpreview.md) | Built the preview of a content to delivery or of a line of the output file (in external mode). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Built the preview of a content to delivery or of a line of the output file (in external mode). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliveries](sm-delivery-cleanupdeliveries.md) | Specifies that the mid-sourcing server should delete certain deliveries. |
| [CollectLogs](sm-delivery-collectlogs.md) | Creates a table with all the delivery log messages for a list of deliveries |
| [CreateFromModel](sm-delivery-createfrommodel.md) | Creation of a delivery from a template (from its internal name). |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | Publish the transactional message on execution instances. Returns true if the publication is successful and false if not. |
| [DeployTriggerMessages](sm-delivery-deploytriggermessages.md) | Publish the selected transactional messages on the execution instances |
| [DiagnoseHTML](sm-delivery-diagnosehtml.md) | Starts the HTML content diagnostic |
| [DispatchImages](sm-delivery-dispatchimages.md) | Tells the application server to send the images to the mid-sourcing server. |
| [ExecCommand](sm-delivery-execcommand.md) | Execute a command on a delivery. |
| [ExecuteJob](sm-delivery-executejob.md) | Executes a synchronous process on a delivery. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Finalize the analysis of a delivery in mid-sourcing mode. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Retrieve the last logs from the journal and the delivery status. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Returns the list of files found on the server associated with the delivery. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Retrieve the delivery logs modified last in mid-sourcing-mode. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | Retrieve the status of the deliveries modified last in mid-sourcing-mode. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Returns the Xtk key of the mid server |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Obtains the URL of an HTML mirror page. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Converts HTML content into plain text |
| [ImagePublishing](sm-delivery-imagepublishing.md) | Performs the post-processing: moving the image to a specified folder and making it available online |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | Install a transactional message template on the execution instance. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Must be called at the end of message preparation except for mid-sourcing (private method). |
| [LaunchFCP](sm-delivery-launchfcp.md) | Starts a Proof copy for a delivery |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Load a list of components for preprocessing with dependencies (personalization blocks, options, additional script objects, etc.). |
| [Pause](sm-delivery-pause.md) | Suspend a delivery. |
| [Play](sm-delivery-play.md) | Start a delivery. |
| [Prepare](sm-delivery-prepare.md) | Delivery analysis: Targeting and personalization |
| [PrepareAndStart](sm-delivery-prepareandstart.md) | Analyzes the delivery and executes it straightaway if no errors are encountered |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analyze a delivery. |
| [PrepareMessage](sm-delivery-preparemessage.md) | Message personalization |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | Message personalization |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | Save the images to include in the email in the database |
| [PrepareNotification](sm-delivery-preparenotification.md) | Analyze a notification being added to an existing delivery action |
| [PrepareProof](sm-delivery-prepareproof.md) | Delivery analysis in view of generating a proof |
| [PrepareTarget](sm-delivery-preparetarget.md) | Delivery target count and arbitration |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | Delivery target count and arbitration |
| [PreviewExtraction](sm-delivery-previewextraction.md) | Preview of the extraction file |
| [PrioritizeLogs](sm-delivery-prioritizelogs.md) | Prioritize the delivery log for a list of deliveries |
| [PrioritizeTarget](sm-delivery-prioritizetarget.md) | Delivery target arbitration |
| [QueueNotification](sm-delivery-queuenotification.md) | Request to queue a notification referencing a delivery template. |
| [RecomputeStats](sm-delivery-recomputestats.md) | Recompute delivery and tracking statistics for a delivery action. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | Save URLs of this delivery as URL templates. |
| [Stop](sm-delivery-stop.md) | Stop a delivery in progress. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | Adds information to generate mirror pages for a set of delivery parts. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Adds information to generate mirror pages for a set of delivery parts. |
| [SubmitDelivery](sm-delivery-submitdelivery.md) | Creation and submission of a delivery from a scenario (from its internal name). |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Create and submit a delivery from a scenario (identified by it's internal name). |
| [SubmitJob](sm-delivery-submitjob.md) | Submits a job for a delivery for asynchronous processing |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Submit a delivery in mid-sourcing mode. |
| [SubmitNotification](sm-delivery-submitnotification.md) | Create and submit a notification from a scenario. |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Update the status of the delivery logs, perform error handling and update the delivery counters. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Must be called every time the delivery is been modified in the memory so that other threads have access to an up to date version (private method). |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | Modifies the imageConfig node to take into account the images already on the server. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | Check the consistency of information used in the definition of the waves. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-entity-save.md) | Saves an entity in the database. |
