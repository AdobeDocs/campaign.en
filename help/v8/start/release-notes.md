---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

Adobe Campaign is regularly updated. This regular frequency of updates aims at getting the latest and greatest in your hands, keeping your environment secure and improving your experience with our product. Adobe strongly recommends all customers to upgrade to the latest version. This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) latest releases. Learn more about Campaign versions and updates in [this page](upgrades.md).

As a Managed Cloud Services user, your instance is upgraded by Adobe with every new version. Adobe will contact you and upgrade your environments. Campaign client console **must be upgraded to the same version** as Campaign servers. Learn how to upgrade your client console in [this page](../start/connect.md#upgrade-ac-console).

In addition, as a customer, ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).



## Release 8.6.3 {#release-8-6-3}

_July 30, 2024_

### New features {#new-8-6-3}

* **Rich Push Notification** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 

* Starting this version, with the Service Account (JWT) credential being deprecated by Adobe, Campaign outbound integrations with Adobe solutions and apps now rely on OAuth Server-to-Server credential. [Learn more](release-notes.md#change-8-7-1)

### General improvements {#improvements-8-6-3}

* To increase security over all communication between applications, mTLS is now supported for external API calls.

### Fixes {#fixes-8-6-3}

The following issues are fixed in this release:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Release 8.5.3 {#release-8-5-3}

_May 28, 2024_

### Migration to OAuth Server-to-Server credential {#change-8-5-3}

Starting this version, with the Service Account (JWT) credential being deprecated by Adobe, Campaign outbound integrations with Adobe solutions and apps now rely on OAuth Server-to-Server credential. [Learn more](#change-8-7-1)

### Fixes {#fixes-8-5-3}

The following issues are fixed in this release:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## May updates {#may-updates}

The following change has been released in May and is now available to Campaign v8 users:

* **New Enhanced Security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced Security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling. [Read more](../config/enhanced-security.md)


## Release 8.7.1 {#release-8-7-1}

_May 2, 2024_

>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### New features {#new-8-7-1}

* **Rich Push Notification templates** - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. [Read more](../send/rich-push-ios.md).

* **Branding** -  As a Campaign Standard migrated user, your technical administrators can now define one or several brands to centralize the parameters that affect a brand's identity. This includes the brand logo, the domain of the landing pages' access URL, or message tracking settings. You can create these brands and link them to messages or landing pages. This configuration is managed in templates. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}

* **Rest APIs** - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html){target="_blank"}

* **Dynamic Reporting** - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

### Compatibility updates {#comp-8-7-1}

* Databricks is now supported as an external database with Adobe Campaign Federated Data Access (FDA). Learn more [in this page](compatibility-matrix.md#FederatedDataAccessFDA).

### Migration to OAuth Server-to-Server credential {#change-8-7-1}

Starting this version, with the Service Account (JWT) credential being deprecated by Adobe, Campaign outbound integrations with Adobe solutions and apps now rely on OAuth Server-to-Server credential. Adobe will perform the JWT to OAuth migration for your outbound integrations, such as Campaign-Analytics integration or Experience Cloud Triggers integration.
 
If you have implemented inbound integrations with Campaign, you must migrate your Technical Account as detailed in [this documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Existing Service Account (JWT) credentials will continue to work until **January 27, 2025**.

### General improvements {#improvements-8-7-1}

* Several schemas have been changed from 32 to 64 bits. This only applies to customers migrating from Campaign Standard. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html){target="_blank"}

* In Campaign tables, the following attributes are now populated by default by the server date and time: `lastModified` and `created`. The `createdBy-id` attribute value is now populated with the current login ID by default. Values provided by users in API calls are ignored. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* To increase security over all communication between applications, mTLS is now supported for external API calls.

### Fixes {#fixes-8-7-1}

The following issues are fixed in this release:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054
