---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
TQID: https://experienceleague.adobe.com/Zdo52RLQFbxlRNgE54yLDn3yAMmmOqxKyRhnCJa0Xwg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

## Release 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> Client Console upgrade is mandatory. Learn how to upgrade your Client Console in this [page](../start/connect.md#upgrade-ac-console).

_May 3, 2026_

### Security improvements {#security-8-9-2}

* To maintain optimal security, stability, and compliance, all instances have been upgraded to Debian 13 and PostgreSQL 17.

### Fixes {#fixes-8-9-2}

>[!NOTE]
>
> Fixes listed below have been progressively rolled out across successive 8.9.2 builds. Navigate to the **[!UICONTROL Help > About...]** [menu](upgrades.md#version) to check that you have the latest 8.9.2 (11d1c68) build. Contact your Adobe representative for more information.

* Fixed an issue where event dates in transactional events were incorrectly set due to a data type conversion issue, causing incorrect dates in dynamic reporting. (NEO-93923)
* Fixed an issue where Android and iOS silent push notifications failed during delivery preparation when title and body fields were empty. (NEO-93739)
* Fixed an issue preventing the language field from being captured for Android app registration tokens due to incorrect reconciliation keys. (NEO-93100)
* Fixed an issue where delivery preparation failed when applying custom typology rules with pressure rules. (NEO-94457)
* Fixed an issue where the client console could experience HTTP request processing failures. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* FDA monitoring is now disabled by default to prevent connection log insertion errors. (NEO-94841)
* Fixed an issue where Interaction SOAP calls used for offer redemption could fail with a namespace resolution error. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* Fixed an issue where string fields with length 1 could cause SQL errors in workflow temporary tables on PostgreSQL 17. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* Fixed an issue where the **Display mirror page** option in the Client Console and Web UI could return a "Bad Mirror Page" error. (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* Fixed an issue where the out-of-the-box **Tracking** technical workflow could fail after a multivariant package installation in FFDA deployments. (NEO-94972)
* Fixed an issue where delivery preparation could fail to add any recipients to the target when the delivery template used a weight formula referencing the current delivery. (NEO-94892)
<!-- hotfix -->
* Fixed an issue where workflow enrichments using joins across two consecutive 1-N links could fail with SQL errors after an upgrade. (NEO-94893) 

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* Fixed an issue in the email pipeline which could lead to excessive memory consumption over time. (NEO-95088)
* Fixed an issue where the conflicting email typology rule could incorrectly exclude non-duplicate recipients from a delivery target when seed or proof addresses were used. (NEO-95026)
* Fixed an issue where the out-of-the-box **Offer notification** technical workflow could fail after an upgrade. (NEO-95064)
* The multivariant package installation process has been improved to prevent tracking workflow failures during build upgrades. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* Fixed an issue which could cause the server to crash repeatedly, leading to instance outages. (NEO-95304)
* Fixed an issue where tracking and mirror page links could fail to load deliveries. (NEO-95239)
* Fixed an issue which could cause a redirect loop when logging in to Campaign web applications protected by IMS single sign-on. (NEO-95188)
* Fixed an issue where the delivery creation date was missing from delivery extraction files after saving the delivery. (NEO-95010)
* Fixed an issue where child workflows spawned in high volume could remain stuck in the **Being Edited** state, reducing transactional workflow capacity. (NEO-95131)
* Fixed an issue where the **Read List** activity could overwrite predefined list templates with workflow-generated list structures, causing failures in downstream workflows. (NEO-95103)
* Fixed an issue where push notification feedback handling could cause the server to crash when processing high-volume deliveries. (NEO-95150)
* Fixed an issue where opening the **Data** tab on the `xtk:workflow` schema in the schema explorer could trigger an error message. (NEO-94923)
<!-- hotfixes -->
* Fixed an issue where the **Enrichment** activity could no longer retrieve output attributes from upstream **Subworkflow** activities, causing workflows to fail. (NEO-95151)
* Fixed a tracking data ingestion issue which could prevent delivery status updates and block downstream message processing. (NEO-94666)
* Fixed an issue where certain Client Console actions related to offer propositions could trigger long-running queries on Snowflake databases, causing locks and slowness. (NEO-92936)
* Fixed an issue where custom options for storing encrypted keys could not be configured on Snowflake external accounts. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

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

* Snowflake external accounts now support OAuth2 authentication, providing modern and secure authentication methods for federated data access connections. (NEO-87013) [Read more](../config/external-accounts.md#snowflake-external-accounts)
* Databricks external accounts now support OAuth2 authentication via service principal (non-interactive client credentials flow), providing secure authentication methods for federated data access connections. Interactive OAuth2 authentication will be available in a future release. (NEO-87422) [Read more](../config/external-accounts.md#databricks-external-accounts)
* Fixed workflow file access vulnerabilities by restricting operations to authorized directories, preventing unauthorized access and potential remote code execution. (NEO-88460)
* Added FTP URL allowlisting controls to workflow JavaScript code activities, restricting outbound FTP connections to authorized addresses only. (NEO-89083)

### Other changes {#changes-8-9-1}

* Improved container memory management by implementing automatic workflow throttling during high memory conditions, with intelligent workflow restart capabilities and memory guardrails for non-critical processes. (NEO-89041)
* Added support for asymmetric encryption and decryption functions in Campaign workflows. (NEO-80257)
* Enhanced replication agent performance and memory resilience for large data uploads in FFDA deployments. (NEO-88430)
* The **[!UICONTROL SQL code]** and **[!UICONTROL SQL Data Management]** workflow activities have been improved to better protect PostgreSQL databases and keep your workflows running smoothly when custom SQL is executed from Campaign. Refer to [SQL Data Management](../../automation/workflow/sql-data-management.md#important-notes) and [SQL code](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) for more information and best practices. (NEO-86540)


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