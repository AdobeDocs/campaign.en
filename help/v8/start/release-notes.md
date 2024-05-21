---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest release{#latest-release}

Adobe Campaign is regularly updated. This regular frequency of updates aims at getting the latest and greatest in your hands, keeping your environment secure and improving your experience with our product. Adobe strongly recommends all customers to upgrade to the latest version. 

As a Managed Cloud Services user, your instance is upgraded by Adobe with every new version. Adobe will contact you and upgrade your environments. Campaign client console **must be upgraded to the same version** as Campaign servers. Learn how to upgrade your client console in this [page](../start/connect.md#upgrade-ac-console). 

In addition, as a customer, ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).

## Release 8.7.1 {#release-8-7-1}

_May 2, 2024_

>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA). It is restricted to customers migrating **from Adobe Campaign Standard to Adobe Campaign v8**, and cannot be deployed on any other environment.
>
>As a Campaign Standard user transitioning to Campaign v8, learn more about this transition in [Campaign v8 web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### New features {#new-8-7-1}

* **Rich Push Notification templates** - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. [Read more](../send/rich-push.md).

* **Branding** -  As a Campaign Standard migrated user, your technical administrators can now define one or several brands to centralize the parameters that affect a brand's identity. This includes the brand logo, the domain of the landing pages' access URL, or message tracking settings. You can create these brands and link them to messages or landing pages. This configuration is managed in templates. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html){target="_blank"}

* **Rest APIs** - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html){target="_blank"}

* **Dynamic Reporting** - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### Compatibility updates {#comp-8-7-1}

Databricks is now supported as an external database with Adobe Campaign Federated Data Access (FDA). Learn more [in this page](compatibility-matrix.md#FederatedDataAccessFDA).

### General improvements {#improvements-8-7-1}

* Several schemas have been changed from 32 to 64 bits. This only applies to customers migrating from Campaign Standard. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html){target="_blank"}

* In Campaign tables, the following attributes are now populated by default by the server date and time: `lastModified` and `created`. Values provided by users in API calls are ignored. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Fixes {#fixes-8-7-1}

The following issues are fixed in this release:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

## Release 8.6.2 {#release-8-6-2}

_Feb 23, 2024_

### Fixes {#fixes-8-6-2}

This release fixes the following issue:

* Fixed a performance issue that could occur on the mid-sourcing instance (NEO-72595).

## Release 8.6.1 {#release-8-6-1}

_Feb 14, 2024_

### New features {#new-8-6-1}

* Starting this release, you have access to the new **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. From its intuitive interface, you can quickly access your cloud applications, product features, and services. Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 now integrates with **Adobe Experience Manager as a Cloud Service**, with authoring exclusively available via the Adobe Campaign Web User Interface. [Learn more](../connect/ac-aem.md)

* You can now use your **Adobe Experience Manager Assets library** alongside your Experience Cloud Assets even if the Integration with the Adobe Experience Cloud package is installed on your Adobe Campaign instance. [Learn more](../connect/ac-aem.md#assets-library)

### General improvements {#improvements-8-6-1}

* Campaign v8.6 brings improved throughput for **email deliveries tracking indicators**. With our optimized processes, tracking ingestion and compute time is reduced, and you can check your delivery key indicators much faster.


### Deliverability updates {#deliverability-8-6-1}

* By February 2024, any company sending more than 5,000 email messages through Google or Yahoo! will have to start using an authentication technology known as Domain-based Message Authentication Reporting and Conformance (DMARC). Make sure to have DMARC record set up for all the subdomains that you are using with Adobe Campaign. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html){target="_blank"}

* Starting June 1st, 2024, Google and Yahoo! will be requiring senders to comply with One-Click List-Unsubscribe. Adobe Campaign now supports this option. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Fixes {#fixes-8-6-1}

The following issues are fixed in this release:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789