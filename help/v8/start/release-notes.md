---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

>[!BEGINSHADEBOX]

**In this page**

* Campaign v8.6 - [Release 8.6.4](#release-8-6-4)
* Campaign v8.7 - [Release 8.7.3](#release-8-7-3) 

>[!ENDSHADEBOX]


## Release 8.7.3 {#release-8-7-3}

_Feb 14, 2025_

>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### New features {#features-8-7-3}

* **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Fixes {#fixes-8-7-3}

The following issues are fixed in this release:

NEO-79373, NEO-81908, NEO-83081.


## Release 8.6.4 {#release-8-6-4}

_Jan 15, 2025_

### General improvements {#improvements-8-6-4}

* Campaign application stability has been improved during delivery analysis in the context of an [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md).
* This release comes with improved and strengthened FFDA architecture mechanisms, including key management, staging, and data replication.
* New technical workflows have been introduced for the [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md). These workflows replicate delivery and related data by centralizing parallel replication requests on corresponding tables. These workflow start with `Replicate nms`. [Read more](../architecture/replication.md)
* A new **Enable watchdog supervisor to keep workflow running permanently** option is now available in the workflow properties. When this option is enabled, workflows automatically restart after an error occurred. The restart happens every 30 seconds by default if the workflow is still in error. To adjust this interval, you can create a new `XtkWorkflow_WatchdogTimerTimeout` option and set an Integer data type to specify the new delay. This option should only be enabled in technical workflows. [Read more](../../automation/workflow/workflow-properties.md#execution)

### Security improvements {#security-8-6-4}

Connection with Adobe solutions and apps through the **[!UICONTROL Adobe Experience Cloud]** external account has been updated to reinforce security. 

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Compatibility updates {#comp-8-6-4}

Databricks is now supported as an external database with Adobe Campaign Federated Data Access (FDA). Learn more [in this page](compatibility-matrix.md#FederatedDataAccessFDA).

### Fixes {#fixes-8-6-4}

The following issues are fixed in this release:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

