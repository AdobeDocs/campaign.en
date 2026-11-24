---
title: Campaign options
description: Learn what Campaign options are, where they are stored, and how to use the options documented for Campaign v8
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Campaign options {#campaign-options}

Options are parameters that control how your Campaign instance behaves, for example the default size limit of images in emails, the number of workflows that run at the same time, or the default routing provider of delivery templates. Some options are built in and others are created when needed. The available options depend on the packages installed on your instance. Learn more in [Built-in packages](built-in-packages.md).

>[!CAUTION]
>
>Only modify the options documented in the Campaign documentation, and only as described. Options that are not documented are internal and must not be modified. Modifying options is reserved for expert users.

## Where options are stored {#where-options-are-stored}

Options are stored in the Campaign database, in the **xtkOption** table (schema **xtk:option**). In Campaign Explorer, they are available under **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.

## Use options {#use-options}

1. In Campaign Explorer, browse to **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**.
1. Select the option, then update its value. If the option does not exist, create it with the exact name given in the documentation.
1. Set a value of the type the documentation expects. For example, a text option for the CRM synchronization date, or an integer option for the workflow restart delay.

Some options hold credentials. Encrypt secrets with the `cryptString` function, as described in [Work with Campaign and Adobe Experience Platform landing pages](../connect/ac-aep-landing-pages.md). When you rotate credentials, also rotate the ones stored in options. Learn more in the [credential rotation guide](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Available options {#available-options}

The tables below list the options available in Campaign v8, grouped by area. When another page of the documentation describes an option, the table links to it.

### Deliveries {#delivery-options}

These options control how deliveries are prepared and sent. They cover image and attachment limits, the default routing provider, the mid-sourcing split threshold, the open tracking script, the public server URL, the delivery validity, the handling of duplicates and delayed deliveries, and barcodes. Learn more in [Attaching files](../send/attaching-files.md), [Email parameters](../send/email-parameters.md), [Delivery best practices](../start/delivery-best-practices.md), [Get started with Campaign architecture](architecture.md#split), [Guidance Regarding Email Tracking Pixels](../start/cnil-pixel-tracking.md), and [Send direct LINE messages](../send/line/line.md).

| Option | Description |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Maximum size, in bytes, of an image downloaded from a personalized URL and attached to an email. The default value is 100,000 bytes (100 KB). [Learn more](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | Maximum number of attachments in an email or transactional email template before a warning is displayed. The default value is 1. [Learn more](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | Default error email address of the instance, used when the delivery leaves the error address empty. [Learn more](../send/email-parameters.md) |
| XtkEmail_Characters | Valid characters for an email address. [Learn more](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Default routing provider of new delivery templates. Set it to the name of a split external account to use split delivery by default. [Learn more](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Size from which a delivery is split among multiple mid-sourcing instances. The default value is 100K. [Learn more](architecture.md#split) |
| NmsTracking_OpenFormula | Script that computes the open tracking URL. Define one option per pixel purpose. [Learn more](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | Base URL of the public web application server. Used, for example, to include a web app link in a LINE message. [Learn more](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Default validity period of a delivery, in seconds. |
| NmsBroadcast_RemoveDuplicatesRecipients | Set it to 1 to automatically ignore duplicate recipients. |
| NmsDelivery_ImageServerTimeout | Timeout, in seconds, for getting a response from the server when retrieving an image downloaded from a personalized URL and attached to an email. If the timeout is exceeded, the message cannot be sent. The default value is 60 seconds. |
| NmsDeliveryWizard_ShowDeliveryWeight | Displays the message weight in the delivery assistant. |
| NmsMTA_Alert_Delay | Delay, in minutes, after which a delivery is considered delayed. The default value is 30 minutes. |
| NmsServer_MirrorPageUrl | URL of the mirror page server. It is the default value of email deliveries when the routing definition does not specify a URL. By default, it is identical to the tracking server URL. |
| XtkBarcode_SpecialChar | Enables or disables the support of special characters for Code128 barcodes. |
| XtkSecurity_Restrict_EditXML | Add it with the value 0 to disable the editing of the XML code of deliveries (Edit XML source or Ctrl+F4). |
| NMS_ActivateOwnerConfirmation | Set it to 1 so that the operator in charge of the delivery can confirm the send, when a specific operator or group is designated for starting the delivery. Set it to 0 to deactivate: only the designated operator or group, or an administrator, can then confirm the send. |

### Campaigns and workflows {#campaign-workflow-options}

These options control how campaigns and workflows run. They cover the owner confirmation of a send, the number of jobs processed at the same time, and the check and automatic restart of workflows. They also cover the protection of SQL activities, the default campaign validity, and the logo of exported reports. Learn more in [Marketing campaign deliveries](../../automation/campaigns/marketing-campaign-deliveries.md), [Workflow best practices](../../automation/workflow/workflow-best-practices.md), [Monitor workflow execution](../../automation/workflow/monitor-workflow-execution.md), [Workflow properties](../../automation/workflow/workflow-properties.md), and [SQL code and JavaScript code](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Option | Description |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Create it and set it to 1 so that the campaign owner can confirm the send, even if reviewers are defined. Set it to 0 to deactivate. [Learn more](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Maximum number of delivery, workflow, hypothesis, and simulation jobs that a campaign processes at the same time. The default value is 10. [Learn more](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Number of days between two checks for paused workflows. [Learn more](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Create it as an integer option to change the 30-second interval at which workflows are checked and restarted automatically. [Learn more](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Set it to 0 to deactivate the protection of the SQL code activities against blocked SQL methods. [Learn more](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | List of SQL methods that the SQL activities block or warn about. [Learn more](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Default validity period of a campaign, in seconds. |
| NmsOperation_TimeRange | Time period for the targeting and extraction conditions in scheduled mode. |
| NmsOperation_OperationMgtDebug | Set it to 1 to log the execution information of the operationMgt technical workflow in the workflow audit logs. |
| NmsOperation_DeliveryPreparationWindow | Number of days above which deliveries with an inconsistent status are excluded from the count of running deliveries by the operationMgt technical workflow. The default value is 7. |
| Workflow_AnalysisThreshold | Number of affected records after which table statistics are automatically recomputed. |
| XtkReport_Logo | Logo displayed in the top right-hand corner of exported reports. |

### Email defaults {#email-default-options}

These options define the default sender and reply addresses and labels of your emails. Campaign uses them when a delivery leaves the corresponding field empty. Learn more in [Email parameters](../send/email-parameters.md) and [Work with delivery templates](../send/create-templates.md).

| Option | Description |
|---|---|
| NmsEmail_DefaultFromAddr | Default From address of the instance, used when the delivery leaves it empty. |
| NmsEmail_FromName | Default From label of the instance, used when the delivery leaves it empty. |
| NmsEmail_DefaultReplyToAddr | Default Reply-to address of the instance, used when the delivery leaves it empty. |
| NmsEmail_ReplyToName | Default Reply-to label of the instance, used when the delivery leaves it empty. |
| NmsEmail_DefaultErrorAddr | Default error address of the instance, used when the delivery leaves it empty. [Learn more](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | Syntax of the From address used when sending a message. |
| NmsDelivery_ErrorAddressMasks | Syntax of the error address used when replying to a message. |
| NmsEmail_ExpOrganization | Common name of your organization, used in some warning messages displayed to the recipients. |

### Soft errors and quarantine {#error-options}

These options define when a recipient is put into quarantine after soft errors, which are temporary delivery failures. Learn more in [Quarantine management in Campaign](../send/quarantines.md#soft-error-management) and [Delivery failures in Campaign](../send/delivery-failures.md#retries).

| Option | Description |
|---|---|
| NmsNPAI_EmailMaxError | Maximum number of soft errors accepted on the email channel before the recipient is put into quarantine. |
| NmsNPAI_EmailSignificantErrorDelay | Minimum time that must pass after the previous soft error on the email channel before a new soft error is taken into account. |
| NmsNPAI_MobileMaxError | Maximum number of soft errors accepted on the mobile channel before the recipient is put into quarantine. |
| NmsNPAI_MobileSignificantErrorDelay | Minimum time that must pass after the previous soft error on the mobile channel before a new soft error is taken into account. |

### Channels {#channel-options}

These options define the sender address of direct mail, the settings of the LINE and SMS channels, and the allowed forwarding addresses of inbound email. Learn more in [Send direct mails with Adobe Campaign](../send/direct-mail.md), [Send direct LINE messages with Adobe Campaign](../send/line/line.md), and [Send SMS with Adobe Campaign](../send/sms/sms.md).

| Option | Description |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Lines 1, 3, 4, 6, and 7 of the sender address of direct mail deliveries. |
| NmsLine_AESKey | AES key used by the lineImage servlet to encode URLs in the LINE channel. |
| NmsLine_MessageCenterURL | Message Center server URL used to send welcome messages in the LINE channel. |
| NmsSMS_Priority | Priority of sent SMS messages, transmitted to the SMS gateway. |
| NmsInmail_AllowlistEmails | Authorized forwarding email addresses of the inbound mail processing module, separated by commas. Use * to allow all addresses. |

### Message Center thresholds {#message-center-options}

These options define the thresholds that raise a warning or an alert when the processing of real-time events, which trigger transactional messages, degrades. Each metric has a warning threshold and an alert threshold. The option name ends with Warning or Alert, for example MC_RtEventErrorWarning and MC_RtEventErrorAlert. Learn more in [Campaign Transactional messaging](../send/transactional.md) and [Campaign Transactional messaging settings](../config/transactional-msg-settings.md).

| Option name prefix | Metric |
|---|---|
| MC_RtEventAvgDeliveryTime | Average sending time of real-time events. |
| MC_RtEventAvgProcessTime | Average processing time of real-time events. |
| MC_RtEventAvgQueueTime | Average queuing time of real-time events. |
| MC_RtEventAvgQueue | Average number of queued real-time events. |
| MC_RtEventMaxQueue | Maximum number of queued real-time events. |
| MC_RtEventMinQueue | Minimum number of queued real-time events. |
| MC_RtEventQueue | Queue of pending real-time events. The alert threshold is the critical condition. |
| MC_RtEventError | Processing errors of real-time events. |
| MC_RtEventThroughput | Throughput of real-time events. |

### Data retention and database {#database-options}

The cleanup workflow purges old records to keep the database from growing. These options define how long Campaign keeps each type of data. A purge delay option is created automatically when you change the delay in the interface. If you edit it from the options list, express the value in seconds. Learn more in [General architecture](general-architecture.md) and [Security guidelines](../config/security.md#consent).

| Option | Description |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Delay after which delivery logs (broadlogs) are erased. |
| NmsCleanup_TrackingLogPurgeDelay | Delay after which tracking logs are erased. |
| NmsCleanup_TrackingStatPurgeDelay | Delay after which tracking statistics are erased. |
| NmsCleanup_EventPurgeDelay | Delay after which events are erased. |
| NmsCleanup_EventHistoPurgeDelay | Delay after which the event history is erased. |
| NmsCleanup_EventStatPurgeDelay | Delay after which event statistics are erased. |
| NmsCleanup_PropositionPurgeDelay | Delay after which propositions are erased. |
| NmsCleanup_QuarantineMailboxFull | Delay after which quarantines are erased. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Delay after which recycled deliveries are erased. |
| NmsCleanup_RejectsPurgeDelay | Delay after which rejects are erased. |
| NmsCleanup_VisitorPurgeDelay | Delay after which visitors are erased. |
| NmsCleanup_WorkflowResultPurgeDelay | Delay after which workflow results are erased. |
| XtkCleanup_NoStats | Set it to 1 so that the cleanup workflow does not update the database statistics. |
| WdbcKillSessionPolicy | Behavior of the Unconditional stop of workflows on PostgreSQL. 0 (default): stops the workflow process with no impact on the database. 1: stops the process and cancels the query (pg_cancel_backend). 2: stops the process and terminates the query (pg_terminate_backend). |
| XtkSequence_AutoGeneration | Applies to custom schemas created after this option is set, with autopk="true" and no pkSequence attribute: Campaign generates the sequence automatically. |

### Message Center customization {#message-center-customization}

These options let you customize how Campaign enriches and routes real-time and batch events. Learn more in [Campaign Transactional messaging](../send/transactional.md) and [Campaign Transactional messaging settings](../config/transactional-msg-settings.md).

| Option | Description |
|---|---|
| MC_EnrichmentCustomJs | JavaScript library that enriches events. It must implement enrichRtEvents(aiEventId) for real-time events and enrichBatchEvents(aiEventId) for batch events. Both functions enrich the events and save them in the database. |
| MC_RoutingCustomJs | JavaScript library that routes events. It must implement dispatchRtEvent(iEventId) and dispatchBatchEvent(iEventId), which return the internal name of the transactional message selected for the real-time or batch event. |
| NmsMessageCenter_RoutingBatchSize | Size of the groups used for event routing. |

### Interaction (offer management) {#interaction-options}

These options apply to Campaign Interaction, the offer management module. They control how propositions are written and how the control and execution instances are synchronized. Learn more in [Campaign Interaction - Offer management](../interaction/interaction.md) and in the [maintenance options](../interaction/interaction-architecture.md#maintenance-options) of the Interaction architecture.

| Option | Description |
|---|---|
| NmsInteraction_UseDaemon | Set it to 1 to enable the asynchronous writing of propositions, or to 0 to disable it. |
| `NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>` | Last date that an environment was synchronized on a given instance. Maintenance option of the control instance. |
| `NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>` | Last date that the propositions of a schema were synchronized from one instance to another. Maintenance option of the control instance. |
| NmsInteraction_MapWorkflowId | List of all the generated synchronization workflows. Maintenance option of the control instance. |
| NmsExecutionInstanceId | Identifier of the execution instance. Available on execution instances. |

>[!CAUTION]
>
>Use the maintenance options only for specific maintenance cases.

The following options apply to coupons, which are not available in Enterprise (FFDA) deployments. Learn more in [Personalized coupons](../send/personalized-coupons.md).

| Option | Description |
|---|---|
| NmsModule_CouponsEnabled | Enables coupons. |
| NmsCoupons_MaxPerTransac | Number of coupons updated per SQL transaction. |

### Privacy requests {#privacy-options}

These options control how Campaign processes privacy requests, such as the confirmation of deletions, the number of errors allowed, and how long request data is kept. Learn more in [Manage Privacy requests in Campaign](../start/privacy.md).

| Option | Description |
|---|---|
| Privacy_Request_ConfirmDeletePending | Set it to 1 to confirm each deletion manually in the interface in a second step. Otherwise, data is deleted without confirmation. |
| Privacy_Request_ConfirmDeletePendingDelay | Delay after which a request that waits for deletion confirmation is cancelled. |
| Privacy_Request_MaxErrorAllowed | Maximum number of errors allowed when processing or deleting a privacy request. |
| Privacy_Request_PurgeDelay | Delay between the creation of a request in the queue and the deletion of its data. |

### Audit trail {#audit-trail-options}

The audit trail records the changes made to Campaign entities. Use these options to enable or disable it for an entity, for example to save space in the database. Set the value to 1 to enable the audit trail and to 0 to disable it. Learn more in [Audit trail](../reporting/audit-trail.md#enable-disable-audit-trail).

| Option | Audited entity |
|---|---|
| XtkAudit_Workflows | Workflows |
| XtkAudit_DataSchema | Schemas |
| XtkAudit_Option | Options |
| XtkAudit_Delivery | Deliveries |
| XtkAudit_ExtAccount | External accounts |
| XtkAudit_DeliveryMapping | Delivery mappings |
| XtkAudit_WebApp | Web applications |
| XtkAudit_Offer | Offers |
| XtkAudit_Operator | Operators |
| XtkAudit_Enable_All | All entities |

### Integrations and surveys {#integration-options}

These options store the settings of integrations and surveys: the Adobe Developer Console credentials for landing pages, the last synchronization date of the CRM Connector activity, and the default backup of survey answers. Learn more in [Update Adobe Experience Platform profiles from Adobe Campaign landing pages](../connect/ac-aep-landing-pages.md), [CRM Connectors data synchronization](../connect/crm-data-sync.md), and [Manage answers](../dev/surveys/managing-answers.md).

| Option | Description |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Adobe Developer Console credentials used for landing pages with Adobe Experience Platform. [Learn more](../connect/ac-aep-landing-pages.md) |
| `LASTIMPORT_<instance>_<activity>` | Date of the last synchronization of the generic CRM Connector activity. Create it manually as a text option, in the format `yyyy/MM/dd hh:mm:ss`. [Learn more](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Create it and set it to 1 to save a copy of the raw answers by default for all surveys. [Learn more](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Types of Adobe Experience Manager resources that can be used in Campaign, separated by commas. [Learn more](../connect/ac-aem.md) |
| nmsPipeline_config | Configuration of Adobe Experience Cloud triggers, in JSON format. Create it as a long text option. [Learn more](../connect/ac-triggers.md) |
| TNT_EdgeServer | Adobe Target server used for the integration, set by default. It is the Adobe Target domain server followed by /m2, for example tt.omtrdc.net/m2. [Learn more](../connect/ac-at.md) |
| TNT_TenantName | Name of the Adobe Target organization (client). [Learn more](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Identifiers used by the integration with Adobe Audience Manager. [Learn more](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Options of the Azure Synapse (Azure SQL Data Warehouse) connector. [Learn more](../connect/fda.md) |

## Related topics {#related-topics}

* [Built-in packages](built-in-packages.md)
* [Global principles](general-architecture.md)
* [Credential rotation guide](../../technotes/security/credential-rotation-guide.md)
