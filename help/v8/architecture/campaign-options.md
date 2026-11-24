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

## Options documented for Campaign v8 {#documented-options}

The tables below list the options that the Campaign v8 documentation asks you to use, with a link to the page that describes how.

### Deliveries {#delivery-options}

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

### Campaigns and workflows {#campaign-workflow-options}

| Option | Description |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Create it and set it to 1 so that the campaign owner can confirm the send, even if reviewers are defined. Set it to 0 to deactivate. [Learn more](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Maximum number of delivery, workflow, hypothesis, and simulation jobs that a campaign processes at the same time. The default value is 10. [Learn more](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Number of days between two checks for paused workflows. [Learn more](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Create it as an integer option to change the 30-second interval at which workflows are checked and restarted automatically. [Learn more](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Set it to 0 to deactivate the protection of the SQL code activities against blocked SQL methods. [Learn more](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | List of SQL methods that the SQL activities block or warn about. [Learn more](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |

### Email defaults {#email-default-options}

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

| Option | Description |
|---|---|
| NmsNPAI_EmailMaxError | Maximum number of soft errors accepted on the email channel before the recipient is put into quarantine. |
| NmsNPAI_EmailSignificantErrorDelay | Minimum time that must pass after the previous soft error on the email channel before a new soft error is taken into account. |
| NmsNPAI_MobileMaxError | Maximum number of soft errors accepted on the mobile channel before the recipient is put into quarantine. |
| NmsNPAI_MobileSignificantErrorDelay | Minimum time that must pass after the previous soft error on the mobile channel before a new soft error is taken into account. |

Learn more about soft errors and quarantines in [Delivery failures](../send/delivery-failures.md).

### Message Center thresholds {#message-center-options}

Each real-time event metric has a warning threshold and an alert threshold. The option name ends with Warning or Alert, for example MC_RtEventErrorWarning and MC_RtEventErrorAlert. Learn more about transactional messaging in [Campaign Transactional messaging](../send/transactional.md).

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

### Privacy requests {#privacy-options}

| Option | Description |
|---|---|
| Privacy_Request_ConfirmDeletePending | Set it to 1 to confirm each deletion manually in the interface in a second step. Otherwise, data is deleted without confirmation. |
| Privacy_Request_ConfirmDeletePendingDelay | Delay after which a request that waits for deletion confirmation is cancelled. |
| Privacy_Request_MaxErrorAllowed | Maximum number of errors allowed when processing or deleting a privacy request. |
| Privacy_Request_PurgeDelay | Delay between the creation of a request in the queue and the deletion of its data. |

Learn more about privacy requests in [Manage Privacy requests](../start/privacy.md).

### Audit trail {#audit-trail-options}

Set an audit trail option to 1 to enable the audit trail for an entity, or to 0 to disable it: XtkAudit_Workflows, XtkAudit_DataSchema, XtkAudit_Option, XtkAudit_Delivery, XtkAudit_ExtAccount, XtkAudit_DeliveryMapping, XtkAudit_WebApp, XtkAudit_Offer, XtkAudit_Operator. Use XtkAudit_Enable_All for every entity. Learn more in [Audit trail](../reporting/audit-trail.md#enable-disable-audit-trail).

### Integrations and surveys {#integration-options}

| Option | Description |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Adobe Developer Console credentials used for landing pages with Adobe Experience Platform. [Learn more](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_<instance>_<activity> | Date of the last synchronization of the generic CRM Connector activity. Create it manually as a text option, in the format `yyyy/MM/dd hh:mm:ss`. [Learn more](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Create it and set it to 1 to save a copy of the raw answers by default for all surveys. [Learn more](../dev/surveys/managing-answers.md) |

## Related topics {#related-topics}

* [Built-in packages](built-in-packages.md)
* [Global principles](general-architecture.md)
* [Credential rotation guide](../../technotes/security/credential-rotation-guide.md)
