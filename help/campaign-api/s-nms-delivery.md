# delivery

This schema represents a delivery action or template.

A template is a delivery template including all the necessary parameters. A delivery template can be executed manually from the client console, or executed when an event occurs (started from the scheduler, or programmatically from an SOAP call).

## Methods

| Method | Description |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-AppendDeliveryPart.md) | Add a part to a delivery being prepared. |
| [BuildForward](sm-delivery-BuildForward.md) | Builds the HTML page. |
| [BuildMirror](sm-delivery-BuildMirror.md) | Build the HTML mirror page. |
| [BuildMirrorEx](sm-delivery-BuildMirrorEx.md) | Build the HTML mirror page. |
| [BuildPreview](sm-delivery-BuildPreview.md) | Built the preview of a content to delivery or of a line of the output file (in external mode). |
| [BuildPreviewFromId](sm-delivery-BuildPreviewFromId.md) | Built the preview of a content to delivery or of a line of the output file (in external mode). |
| [BuildTargetDataSchema](sm-delivery-BuildTargetDataSchema.md) |  |
| [CleanupDeliveries](sm-delivery-CleanupDeliveries.md) | Specifies that the mid-sourcing server should delete certain deliveries. |
| [CollectLogs](sm-delivery-CollectLogs.md) | Creates a table with all the delivery log messages for a list of deliveries |
| [CreateFromModel](sm-delivery-CreateFromModel.md) | Creation of a delivery from a template (from its internal name). |
| [DeployTriggerMessageSingle](sm-delivery-DeployTriggerMessageSingle.md) | Publish the transactional message on execution instances. Returns true if the publication is successful and false if not. |
| [DeployTriggerMessages](sm-delivery-DeployTriggerMessages.md) | Publish the selected transactional messages on the execution instances |
| [DiagnoseHTML](sm-delivery-DiagnoseHTML.md) | Starts the HTML content diagnostic |
| [DispatchImages](sm-delivery-DispatchImages.md) | Tells the application server to send the images to the mid-sourcing server. |
| [ExecCommand](sm-delivery-ExecCommand.md) | Execute a command on a delivery. |
| [ExecuteJob](sm-delivery-ExecuteJob.md) | Executes a synchronous process on a delivery. |
| [FinalizeMidPreparation](sm-delivery-FinalizeMidPreparation.md) | Finalize the analysis of a delivery in mid-sourcing mode. |
| [GetDeviceList](sm-delivery-GetDeviceList.md) |  |
| [GetDlStatusAndLogs](sm-delivery-GetDlStatusAndLogs.md) | Retrieve the last logs from the journal and the delivery status. |
| [GetFilesToDownload](sm-delivery-GetFilesToDownload.md) | Returns the list of files found on the server associated with the delivery. |
| [GetMidBroadLogs](sm-delivery-GetMidBroadLogs.md) | Retrieve the delivery logs modified last in mid-sourcing-mode. |
| [GetMidDeliveries](sm-delivery-GetMidDeliveries.md) | Retrieve the status of the deliveries modified last in mid-sourcing-mode. |
| [GetMidXtkKey](sm-delivery-GetMidXtkKey.md) | Returns the Xtk key of the mid server |
| [GetMirrorURL](sm-delivery-GetMirrorURL.md) | Obtains the URL of an HTML mirror page. |
| [GetSeedList](sm-delivery-GetSeedList.md) |  |
| [HtmlToText](sm-delivery-HtmlToText.md) | Converts HTML content into plain text |
| [ImagePublishing](sm-delivery-ImagePublishing.md) | Performs the post-processing: moving the image to a specified folder and making it available online |
| [InstallTransactionalMessage](sm-delivery-InstallTransactionalMessage.md) | Install a transactional message template on the execution instance. |
| [InvalidateDeliveryCache](sm-delivery-InvalidateDeliveryCache.md) | Must be called at the end of message preparation except for mid-sourcing (private method). |
| [LaunchFCP](sm-delivery-LaunchFCP.md) | Starts a Proof copy for a delivery |
| [LoadExpandedContents](sm-delivery-LoadExpandedContents.md) | Load a list of components for preprocessing with dependencies (personalization blocks, options, additional script objects, etc.). |
| [Pause](sm-delivery-Pause.md) | Suspend a delivery. |
| [Play](sm-delivery-Play.md) | Start a delivery. |
| [Prepare](sm-delivery-Prepare.md) | Delivery analysis: Targeting and personalization |
| [PrepareAndStart](sm-delivery-PrepareAndStart.md) | Analyzes the delivery and executes it straightaway if no errors are encountered |
| [PrepareFromId](sm-delivery-PrepareFromId.md) | Analyze a delivery. |
| [PrepareMessage](sm-delivery-PrepareMessage.md) | Message personalization |
| [PrepareMessageImpl](sm-delivery-PrepareMessageImpl.md) | Message personalization |
| [PrepareMultipartRelated](sm-delivery-PrepareMultipartRelated.md) | Save the images to include in the email in the database |
| [PrepareNotification](sm-delivery-PrepareNotification.md) | Analyze a notification being added to an existing delivery action |
| [PrepareProof](sm-delivery-PrepareProof.md) | Delivery analysis in view of generating a proof |
| [PrepareTarget](sm-delivery-PrepareTarget.md) | Delivery target count and arbitration |
| [PrepareTargetImpl](sm-delivery-PrepareTargetImpl.md) | Delivery target count and arbitration |
| [PreviewExtraction](sm-delivery-PreviewExtraction.md) | Preview of the extraction file |
| [PrioritizeLogs](sm-delivery-PrioritizeLogs.md) | Prioritize the delivery log for a list of deliveries |
| [PrioritizeTarget](sm-delivery-PrioritizeTarget.md) | Delivery target arbitration |
| [QueueNotification](sm-delivery-QueueNotification.md) | Request to queue a notification referencing a delivery template. |
| [RecomputeStats](sm-delivery-RecomputeStats.md) | Recompute delivery and tracking statistics for a delivery action. |
| [SaveUrlInfo](sm-delivery-SaveUrlInfo.md) | Save URLs of this delivery as URL templates. |
| [Stop](sm-delivery-Stop.md) | Stop a delivery in progress. |
| [StoreMirrorPageInfo](sm-delivery-StoreMirrorPageInfo.md) | Adds information to generate mirror pages for a set of delivery parts. |
| [StoreMirrorPageInfoEx](sm-delivery-StoreMirrorPageInfoEx.md) | Adds information to generate mirror pages for a set of delivery parts. |
| [SubmitDelivery](sm-delivery-SubmitDelivery.md) | Creation and submission of a delivery from a scenario (from its internal name). |
| [SubmitDeliveryById](sm-delivery-SubmitDeliveryById.md) | Create and submit a delivery from a scenario (identified by it's internal name). |
| [SubmitJob](sm-delivery-SubmitJob.md) | Submits a job for a delivery for asynchronous processing |
| [SubmitMidSourcing](sm-delivery-SubmitMidSourcing.md) | Submit a delivery in mid-sourcing mode. |
| [SubmitNotification](sm-delivery-SubmitNotification.md) | Create and submit a notification from a scenario. |
| [UpdateBroadLogs](sm-delivery-UpdateBroadLogs.md) | Update the status of the delivery logs, perform error handling and update the delivery counters. |
| [UpdateCachedDelivery](sm-delivery-UpdateCachedDelivery.md) | Must be called every time the delivery is been modified in the memory so that other threads have access to an up to date version (private method). |
| [UpdateImageConfig](sm-delivery-UpdateImageConfig.md) | Modifies the imageConfig node to take into account the images already on the server. |
| [ValidateWavesDefinition](sm-delivery-ValidateWavesDefinition.md) | Check the consistency of information used in the definition of the waves. |

## Generic Methods

| Method | Description |
| --- | --- |
| [create](f-create.md) | Creates a new entity corresponding to a given schema. |
| [load](f-load.md) | Loads and returns an entity corresponding to a given schema and key. |
| [save](m-Entity-save.md) | Saves an entity in the database. |
