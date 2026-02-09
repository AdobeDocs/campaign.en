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
* [Content experiments - A/B testing](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"} 
* [Continuous delivery activity](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"} 
* [Campaign approval management](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"} 

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

* Fixed an issue where the database structure could not be updated after sysFilter changes. (NEO-93306)
* Fixed an issue where dynamic report data was missing after migration. (NEO-92962)
* Fixed an issue where delivery status was not updating correctly. (NEO-92908)
* Fixed an issue related to the Databricks FDA Use Catalog restriction. (NEO-92900)
* Fixed an issue which could cause HTML layout errors in Outlook Windows desktop. (NEO-92611)
* Fixed a data integrity issue where delivery primary keys were duplicated on the mid instance after an upgrade. (NEO-92424)
* Fixed an issue where links could not be disabled in the Tracking & Images dialog box in a delivery. (NEO-92381)
* Fixed an issue where the nms.subscribtion.RecipientSubscribe() function did not work for bulk subscription. (NEO-92308)
* Fixed an issue where delivery failures occurred due to missing delivery parts after an upgrade. (NEO-92278)
* Fixed an issue in the tracking workflow where duplicate status errors and SQL syntax errors prevented tracking indicators from being updated. (NEO-92239)
* Fixed an issue where enumeration field labels were missing or displayed incorrectly in lists created via workflow when using dbEnum fields. (NEO-91158)
* Fixed an issue where the RT publish/unpublish dialog did not close and froze. (NEO-91038)
* Fixed an issue which occurred for recipients with the "Taken into account by the Service provider" status. (NEO-90927)
* Fixed an issue where the (un)subscription origin was missing for opt-out links. (NEO-90714)
* Fixed an issue where adding coupons failed delivery preparation. (NEO-90547)
* Fixed an issue where the Insert Reject Count was not accurately reflected in the Audit tab. (NEO-90318)
* Fixed a security issue that could cause application denial of service. (NEO-89984)
* Fixed an issue where the downloaded PDF of the Hotclick report was broken. (NEO-89954)
* Resolved an SSL error that occurred after an upgrade, causing unexpected EOF while reading errors. (NEO-89108)
* Fixed an issue where data could not be queried in a data schema after an upgrade. (NEO-88663)
* Fixed an error that occurred when concatenating a "char" field in PostgreSQL 15. (NEO-88028)
* Fixed an issue where the order of delivery template variables changed when saving or duplicating the template. (NEO-87845)
* Fixed an issue where creating a new Data Library schema caused the Web interface to crash. (NEO-87816)
* Fixed an issue where with complement sets in the Deduplication activity. (NEO-87711)
* Fixed a request for installation package without X11 dependency. (NEO-87471)
* Fixed an issue where segment codes could not be used in dynamic reports. (NEO-87276)
* Fixed an issue where workflows got stuck in the Update Data activity. (NEO-87252)
* Fixed an issue where BigQuery was using an incorrect timezone. (NEO-86622)
* Fixed a JavaScript error that occurred while evaluating the 'mcSynch_mcExec1/jsReplicateUrl' script. (NEO-86553)
* Fixed an issue where duplicate events appeared in the eventHisto table due to an incorrect identifier calculation method. (NEO-86544)
* Fixed an issue where the Advanced tab was not showing for iOS Push upon copy. (NEO-86231)
* Fixed an issue where the replicate reference tables workflow failed in replicating the nms:delivery schema. (NEO-85884)
* Fixed an issue where null domain errors corresponding to MXIP addresses appeared in error logs while sending deliveries. (NEO-85238)
* Fixed an issue where technical delivery templates were not refreshed after changes made to options. (NEO-84149)
* Fixed an error in the out-of-the-box Billing workflow. (NEO-83624)
* Fixed an issue with exclusion of duplicates based only on the primary key of targeted records. (NEO-82910)
* Fixed discrepancies in Campaign Web UI reports where tracking statistics displayed different values compared to the console. (NEO-82339)
* Fixed an issue where the lastmodified date changed even if the record should not be updated in the Update Data activity. (NEO-82002)
* Fixed an issue where adding new attributes in a list caused workflows reading the list to fail. (NEO-80258)
* Fixed an issue where the Tracking Indicators report displayed incorrect values for distinct opens. (NEO-79466)