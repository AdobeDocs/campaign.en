---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

## Release 8.8.2 {#release-8-8-2}

_Oct 9, 2025_

>[!AVAILABILITY]
>
>This release is in **Limited Availability** (LA).

### New features {#features-8-8-2}

The **new SMS sending connector** is now available for [Campaign FFDA deployments](../architecture/enterprise-deployment.md). Refer to the [detailed documentation](../send/sms/sms.md). 

This release also comes with a set of functionalities available with the Campaign Web user interface:

* [Profile Enrichment in Transactional Messages](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"} 
* [Multilingual Capabilities for Transactional Messaging, Push Notifications and SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Refer to the Campaign Web UI [release notes](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"}

### Fixes {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Fixed an issue which could lead the database cleanup workflow to fail. (NEO-87949)
* Fixed an issue in Distributed Marketing where tracking data was not recorded for collaborative campaign deliveries. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Fixed an issue which could prevent personalization in fragments from working correctly. (NEO-88161)
* Fixed an issue, after migrating to the new Redshift ODBC connector, which could lead the Split workflow activity to fail with SQL errors. (NEO-87466)
* Fixed an issue which could cause inaccurate exclusion counts in workflows. (NEO-89207)
* Fixed an issue which could cause inaccurate click indicators for Push notifications. (NEO-89503)
* Fixed an issue where SMS delivery logs were not updated correctly, preventing accurate status reporting in Adobe Campaign. (NEO-88479)
* Fixed an issue where French quotes were incorrectly converted to English quotes in delivery content. (NEO-89631)
* Fixed an issue where the Real-Time Server returned an incorrect response code for invalid IMS tokens instead. (NEO-87428)
* Fixed an issue where delivery statistics for Email and SMS were not fully recomputed, causing inaccurate success indicators. (NEO-88106)
* Fixed an issue with the new SMS sending connector where delivery logs were incorrectly assigning delivery status for a small subset of messages. (NEO-89581)
* Fixed an issue with the new SMS sending connector where success metrics deliveries were not updating correctly on both marketing and mid servers. (NEO-89850)
* Fixed a synchronization issue between the Real-Time and Marketing instances which caused missing tracking logs and incorrect reporting. (NEO-90247)
* Fixed a workflow enrichment issue which could cause errors when selecting fields across two consecutive 1-N links in custom schemas. (NEO-87682)

