---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

## Release 8.6.4 {#release-8-6-4}

_Jan 15, 2025_

### General improvements {#improvements-8-6-4}

* Campaign application stability has been improved during delivery analysis in the context of an [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md).
* This release comes with improved and strengthened FFDA architecture mechanisms, including key management, staging, and data replication.
* New technical workflows have been introduced for the [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md). These workflows replicate delivery and related data by centralizing parallel replication requests on corresponding tables. These workflow start with `Replicate nms`.
* A new **Enable watchdog supervisor to keep workflow running permanently** option is now available in the workflow properties. When this option is enabled, workflows automatically restart after an error occurred. The restart happens every 30 seconds by default. To adjust this interval, you can create a new `XtkWorkflow_WatchdogTimerTimeout` option and set an Integer data type to specify the new delay. This option should only be enabled in technical workflows.

### Security improvements {#security-8-6-4}

Connection with Adobe solutions and apps through the **[!UICONTROL Adobe Experience Cloud]** external account has been updated to reinforce security. 

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Compatibility updates {#comp-8-6-4}

Databricks is now supported as an external database with Adobe Campaign Federated Data Access (FDA). Learn more [in this page](compatibility-matrix.md#FederatedDataAccessFDA).

### Fixes {#fixes-8-6-4}

The following issues are fixed in this release:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-83096, NEO-83081.

## Release 8.7.2 {#release-8-7-2}

_Sept 3, 2024_

>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### New features {#new-8-7-2}

* **New SMS sending connector** - The SMS sending connector has been modernized and improved to enable transceiver mode SMPP connections, enable persistent SMPP connections, and ensure better compatibility for environments transitioning from Adobe Campaign Standard. A new SMS External account is now available for all new SMS implementations. Existing implementation are still supported, however recommendation is to move to this new modern and extended connector. [Read more](../send/sms/sms.md). 

* **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 

* **Branding** - Branding options are now available for all channels, including SMS and Direct mail. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}

### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.