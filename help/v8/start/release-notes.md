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

As a Managed Cloud Services user, your instance is upgraded by Adobe with every new release. Adobe will contact you and upgrade your environments. Campaign client console **must be upgraded to the same version** as Campaign servers. Learn how to upgrade your client console in this [page](../start/connect.md#upgrade-ac-console). 

In addition, as a customer, ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).


## Release 8.6.1 {#release-8-6-1}

_Feb 14, 2024_


### New features {#new-8-6-1}

* Starting this release, you have access to the new **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. From its intuitive interface, you can quickly access your cloud applications, product features, and services. Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 now integrates with **Adobe Experience Manager as a Cloud Service**, with authoring exclusively available via the Adobe Campaign Web User Interface.

* You can now use your **Adobe Experience Manager Assets library** alongside your Experience Cloud Assets even if the Integration with the Adobe Experience Cloud package is installed on your Adobe Campaign instance.


### General improvements {#improvements-8-6-1}

* Campaign v8.6 brings improved throughput for **email deliveries tracking indicators**. With our optimized processes, tracking ingestion and compute time is reduced, and you can check your delivery key indicators much faster.


### Deliverability updates {#deliverability-8-6-1}

* Since February 1st, 2024, Google and Yahoo! are requiring that you have a DMARC record for any domain you use to send email to them. Make sure to have DMARC record set up for all the subdomains that you are using with Adobe Campaign. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html){target="_blank"}

* Starting June 1st, 2024, Yahoo! and Gmail will be requiring senders to comply with One-Click List-Unsubscribe. Adobe Campaign now supports this option. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Fixes {#fixes-8-6-1}

The following issues are fixed in this release:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789