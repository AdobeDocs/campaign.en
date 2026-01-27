---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

## Release 8.9.1 {#release-8-9-1}

_Jan 27, 2026_

>[!CAUTION]
>
> Client Console upgrade is mandatory. Learn how to upgrade your Client Console in this [page](../start/connect.md#upgrade-ac-console).

### New features {#new-8-9-1}

The **new SMS sending connector** is now available to all customers (GA). Refer to the [detailed documentation](../send/sms/sms.md). 

This release comes with a set of functionalities available with the Campaign Web user interface:

* [Multilingual delivery capabilities (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Profile Enrichment in Transactional Messages (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"} 
* [Adobe Experience Manager live and language copies](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"} 
* [Content experiments - A/B testing](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html)
* [Continuous delivery activity](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html)
* [Campaign approval management](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html)

Refer to the Campaign Web UI [release notes](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"}

### Security improvements {#security-8-9-1}

* Snowflake external accounts now support OAuth2 authentication, providing modern and secure authentication methods for federated data access connections. (NEO-87013)
* Fixed workflow file access vulnerabilities by restricting operations to authorized directories, preventing unauthorized access and potential remote code execution. (NEO-88460)
* Added FTP URL allowlisting controls to workflow JavaScript code activities, restricting outbound FTP connections to authorized addresses only. (NEO-89083)

### Other changes {#changes-8-9-1}

* Improved container memory management by implementing automatic workflow throttling during high memory conditions, with intelligent workflow restart capabilities and memory guardrails for non-critical processes. (NEO-89041)
* Added support for asymmetric encryption and decryption functions in Campaign workflows. (NEO-80257)
* Enhanced replication agent performance and memory resilience for large data uploads in FFDA deployments. (NEO-88430)


### Fixes {#fixes-8-9-1}

* Fixed an issue where dynamic reports displayed incorrect counts when grouping by certain columns. (NEO-86898)
* Resolved data discrepancies between dynamic reports and actual campaign data. (NEO-88068)
* Fixed concatenation issues with PostgreSQL "char" field types that caused unexpected results in queries. (NEO-87769)
* Corrected an issue where the JavaScript logInfo command did not properly handle certain parameters. (NEO-88263)
* Resolved synchronization hang issues in Message Center real-time event processing. (NEO-88330)
* Fixed an issue where the Visual Editor automatically reformatted HTML content, causing layout changes. (NEO-88409)
* Corrected a problem where the Deduplication activity failed to work properly with temporary schemas. (NEO-88577)
* Fixed an issue preventing seed addresses from being generated when sending proofs. (NEO-88720)
* Improved PostgreSQL query performance by optimizing partition column handling. (NEO-88771)
* Resolved an issue where file transfer activities did not properly handle line continuation characters. (NEO-88812)
* Enhanced PostgreSQL query optimization for better performance in large datasets. (NEO-88885)
* Fixed a "Permission denied" error that prevented hybrid campaigns from opening. (NEO-88955)
* Extended barcode feature support to handle longer text strings. (NEO-88958)
* Corrected an error in campaign logs that occurred when using proofs with recurring deliveries. (NEO-88976)
* Fixed an issue that affected email sending operations in certain scenarios. (NEO-89019)
* Resolved an issue where workflow start mode unexpectedly changed from Immediate to Normal. (NEO-89025)
* Fixed errors that occurred when running the Update Data activity in specific conditions. (NEO-89031)
* Corrected an issue where the Update Data activity lost custom schema metadata. (NEO-89056)
* Fixed a validation error that occurred during delivery preparation. (NEO-89063)
* Resolved invalid SQL generation when queries contained filters on 1-1 link relationships. (NEO-89065)
* Fixed an issue where the Incremental Query activity did not respect the configured size limit. (NEO-89066)
* Improved workflow performance in FFDA deployments for large-scale operations. (NEO-89098)
* Enhanced memory management and stability for workflow processes. (NEO-89105)
* Enabled strict column validation for web forms to prevent data inconsistencies. (NEO-89111)
* Resolved Message Center synchronization issues that caused processing delays. (NEO-89138)
* Fixed errors in the "Refresh for Deliverability" workflow that prevented proper execution. (NEO-89160)
* Corrected errors that occurred when executing JavaScript code activities in workflows. (NEO-89169)
* Removed hardcoded Snowflake warehouse configurations to allow proper external account settings. (NEO-89201)
* Fixed 403 Forbidden errors that occurred during workflow file transfer operations. (NEO-89226)
* Optimized slow queries on the recipient table in FFDA deployments. (NEO-89268)
* Fixed an issue where incremental query activities ignored configured schedules. (NEO-89317)
* Resolved access errors when opening campaigns in hybrid environments. (NEO-89320)
