---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) **latest releases**. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md). Other releases are listed in the Previous releases section of this documentation.

## Release 8.8.1 {#release-8-8-1}

_July 9, 2025_

### New features {#features-8-8-1}

Previously released for a small set of customers, the following capability is now available to all Campaign FDA environments:

* **New SMS sending connector** - The SMS sending connector has been modernized and improved to enable transceiver mode SMPP connections, enable persistent SMPP connections, and ensure better compatibility. A new SMS External account is now available for all new SMS implementations. Existing implementation are still supported, however recommendation is to move to this new modern and extended connector. [Read more](../send/sms/sms.md)

    >[!NOTE]
    >
    >This feature is **not** available for [Campaign FFDA deployments](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Previously released in Limited Availability, the following capability is now available **on demand**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **Rest APIs** - You can now use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. The Transactional Messaging REST API is also available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. Event-based Transactional APIs are also available for Emails. [Read more](../dev/api/get-started-apis.md)

    >[!NOTE]
    >
    >This feature is **not** available for [Campaign FFDA deployments](../architecture/enterprise-deployment.md).

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

In addition to the features listed above, this release also comes with a set of functionalities available Campaign the Web user interface:

* [Multilingual delivery creation](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [Delivery alerting](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [Landing pages improvements](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [Dynamic Reporting](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (on-demand only)
* [Centralized Branding](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"} (on-demand only)

Refer to the Campaign Web UI [release notes](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html){target="_blank"} 

### General improvements {#improvements-8-8-1}

* Microsoft Fabrics is now supported as an external database with Adobe Campaign Federated Data Access (FDA). [Read more](../config/external-accounts.md#transfer-data-external-accounts)
* Campaign v8 now supports Android 15 and iOS 18 for Push Notifications. [Read more](../start/compatibility-matrix.md#MobileSDK)
* Cloud databases are now supported in addition to the on-premise databases for Secure Virtual Private Network tunneling. [Read more](../config/enhanced-security.md#vpn-databases)
* A new set of "Provider ID" fields has been added in the "Incoming traffic" section of the SMS 2.0 connector. [Read more](../send/sms/smpp-external-account.md#incoming-traffic)
* Unsubscribed recipients through the "mailto" List-Unsubscribe method are no longer sent to quarantine. They are either unsubscribed from the service associated with the delivery, or sent to the denylist (profile's "No longer contact" section) if no service was defined for the delivery. [Read more](../send/quarantines.md)
* A revamped version of the inbox rendering report is now available in the Adobe Campaign client console. [Read more](../send/inbox-rendering.md)

### Fixes {#fixes-8-8-1}

* Fixed an issue where auto-replies were not being received due to an invalid validity period in SMS 2.0. This ensures proper message delivery post-migration. (NEO-88088)
* Resolved a problem in SMS 2.0 where certain fields in the `inSms` table were not being updated correctly, ensuring accurate data insertion for SMS functionalities. (NEO-87906)

<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
-->

* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
* Fixed database cleanup workflow failures due to missing or incorrect column references in SQL queries. This ensures proper purging of logs and visitor data. (NEO-86813)
* Resolved an issue where event dates were missing in delivery logs. This fix ensures accurate event date population, critical for scheduled triggers and workflows. (NEO-86708)
* Fixed SMS delivery log insertion issues in SMS 2.0, ensuring proper logging in the `nmsBroadLogMid` table. (NEO-86556)
* Addressed file extraction issues with external delivery mode in Direct Mail templates, ensuring compatibility and functionality. (NEO-86520)
* Resolved delivery processing issues involving split routing across multiple MID instances, ensuring accurate delivery status updates and throughput. (NEO-86500)
* Fixed missing tracking data in dynamic reports post-migration from Campaign Standard to Campaign v8, ensuring accurate reporting for delivery tracking logs. (NEO-86419)
* Resolved workflow triggering issues where workflows were executing twice, causing duplicate key violations. This fix ensures proper event handling and execution. (NEO-86154)
* Fixed compatibility issues with Redshift OOTB SQL functions post-deployment, ensuring proper execution of functions like `GetDate()` in workflows. (NEO-85834)
* Addressed rendering issues in email builds where images disappeared when URLs were attached. This fix ensures proper image display in inbox previews. (NEO-85716)
* Corrected rendering of curly close quotes in WebUI, ensuring accurate character display in email deliveries. (NEO-85687)
* Fixed mirror page link functionality, ensuring proper navigation between language variants within mirror pages. (NEO-85625)
* Resolved date format issues in web app date pickers, ensuring compatibility with Japanese date formats (`yyyy-mm-dd`). (NEO-85234)
* Fixed post-processing workflow issues with alternate routing setups in midsourcing, ensuring proper workflow execution. (NEO-85111)
* Improved Android delivery throughput when using waves, ensuring delivery parts are processed in the correct order based on scheduling. (NEO-84324)
* Fixed delivery preparation failures due to null processing errors in `to_varchar` function, ensuring smooth campaign launches. (NEO-84108)
* Resolved SFTP connection issues caused by outdated `libcurl` and `libssh2` versions, ensuring compatibility with Azure-hosted SFTP servers. (NEO-84038)
* Fixed Snowflake FDA connector issues involving keypair authentication errors, ensuring successful database connections. (NEO-84024)
* Addressed typology rule functionality issues, ensuring proper application of pressure rules in PUSH deliveries. (NEO-84010)
* Resolved BigQuery query errors caused by mismatched date and timestamp comparisons post-upgrade, ensuring compatibility with filtering conditions. (NEO-83826)
* Resolved an issue where delivery activities would fail when resuming paused deliveries due to personalization errors. This fix ensures smoother delivery workflows and prevents errors related to paused activities. (NEO-83809)
* Fixe an issue in FFDA, when using the "target record load query" option. Support for "order by" and "where" clauses was added. (NEO-83793)
* Addressed recurring delivery failures caused by null values being written to non-nullable columns in the broadLogRcp table. This fix improves delivery reliability and prevents errors during live campaigns. (NEO-83729)
* Resolved an issue where seed addresses were duplicated during delivery preparation, leading to discrepancies in message counts. This fix ensures accurate targeting and prevents duplication errors. (NEO-83703)
* Fixed a critical issue where production deliveries were sent after their validity period, potentially causing legal concerns. Deliveries now adhere strictly to their defined validity periods. (NEO-83350)
* Addressed a space issue encountered while loading large data volumes into Teradata tables. This fix optimizes data processing and resolves intermittent errors in production environments. (NEO-83252)
* Resolved a technical workflow failure related to SendMetricsToNewRelic errors, which caused delays in RT event processing. This fix ensures smoother workflow execution and prevents event backlogs. (NEO-83143)
* Fixed a database cleanup workflow failure caused by ID-to-UUID conversion issues in FFDA interaction instances. This update ensures proper cleanup operations and reduces system load. (NEO-83138)
* Resolved delivery failures caused by constraints on seed-member internal name lengths. This fix allows for longer internal names without impacting delivery personalization. (NEO-83044)
* Fixed an issue where deliveries were getting stuck in personalization pending due to random errors. This update ensures smoother personalization processes and reliable delivery execution. (NEO-82781)
* Addressed an issue where offer propositions could not be reviewed in the console due to API errors and slowness. This fix improves UI responsiveness and ensures proper offer functionality. (NEO-82742)
* Resolved intermittent crashes in the Adobe Campaign console when using custom delivery objects. This fix ensures stability and reliability when working with custom workflows. (NEO-82675)
* Fixed slow processing and workflow failures reported after migrating from v7 to v8. This update optimizes campaign workflows and ensures timely execution. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Fixed a critical issue where MTA child processes were stuck, blocking Push and WhatsApp deliveries. This update ensures smoother communication workflows and prevents delivery bottlenecks. (NEO-82351)
* Addressed a data migration issue where string fields from GCP tables caused errors during updates to Teradata. This fix eliminates the need for workarounds and improves workflow efficiency. (NEO-82260)
* Updated database cleanup logic to account for primary databases in FFDA instances, preventing unnecessary attempts to purge non-existent tables. This fix optimizes cleanup operations. (NEO-81879)
* Resolved console crashes caused by using subworkflows in combination with enum fields. This fix ensures stability when working with enriched workflows. (NEO-81864)
* Fixed an issue where sub-affinity fields in target mappings were incorrectly modified after delivery duplication, causing workflow failures. This update ensures consistent sub-affinity values. (NEO-81809)
* Added support for wildcard characters in file transfer activities in Adobe Campaign Classic v8, enabling users to upload files with dynamic names (e.g., `abc_*`) in workflows. (NEO-81758)
* Introduced an option to enable the `content-available` flag in iOS push notifications for Adobe Campaign Classic v8. This enhancement allows mobile apps to store notifications in the inbox and supports background updates, addressing delivery discard issues caused by APNS limitations. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Added a timeout configuration option for BigQuery connections in Adobe Campaign Classic v8. This enhancement allows users to adjust the timeout period for queries, resolving issues with query failures due to default timeout limits. (NEO-81222)
* Fixed an intermittent issue where mirror page URLs failed for deliveries sent via Split and Alternate routing external accounts after v8 migration. The underlying delivery parts are now correctly copied into `mirrorPageInfo`. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Fixed the "Access the new Web UI" button in the client console to point to the correct URL (`https://experience.adobe.com`) for production instances. This resolves issues with invalid URLs in production environments. (NEO-80673)
* Fixed an issue in the Split activity where using both Sorting and Size (as a percentage of the segment) caused SQL errors. The functionality now works correctly. (NEO-80432)
* Addressed a crash issue in workflows using `CCurlAzureBlobStorage::UploadStream`. The workflows now execute without segmentation faults during Azure Blob Storage uploads. (NEO-79598)
* Resolved an issue where mirror pages were not viewable from the client console in production environments. Mirror page links now work correctly in both email and console views. (NEO-78946)
* Fixed a delivery log issue where some logs were incorrectly marked as "Delivery canceled" despite successful message delivery. The root cause related to contact date and event date discrepancies has been addressed. (NEO-78933)
* Updated the `com.google.code.gson:gson` library to improve security. (NEO-78299)
* Resolved duplicate key constraint errors in FDA connection logs (`nmsconnectionlogs`) that caused workflow failures. The insertion logic has been adjusted to prevent duplicate IDs. (NEO-78050)
* Fixed an issue where quarantined email addresses were incorrectly flagged as mobile in the address table, causing delivery analysis errors. The reconciliation logic between delivery objects has been corrected. (NEO-76986)
* Addressed a delivery preparation failure when using control groups with an Oracle database. The SQL query generation has been corrected to ensure compatibility with Oracle databases. (NEO-76947)
* Resolved delivery failures caused by simultaneous folder creation during new month transitions. The delivery folder creation logic has been adjusted to prevent duplicate key violations. (NEO-76824)
* Fixed inconsistent timezone conversion issues in Teradata external accounts. The displayed timestamps now align correctly with the configured timezone settings. (NEO-76716)
* Improved database cleanup workflows to handle large datasets efficiently. A new approach using row IDs and bind variables has been implemented to optimize deletion performance. (NEO-76439)
* Resolved an issue where external deliveries with the "Other" channel did not generate output files. The delivery properties now correctly include the file path for generated files. (NEO-75962)
* Fixed errors in the `ffdaReplicateStagingData` workflow caused by large data updates. Timeout settings and table size management have been optimized to prevent workflow failures. (NEO-75643)
* Addressed an issue where previewing direct mail output files caused dashboards to turn blank. The dashboard now displays correctly after file previews. (NEO-75359)
* Enhanced tracking indicators for push notifications to include clicks and opens. Indicators such as `@recipientClick`, `@personClick`, and `@totalRecipientClick` now account for mobile notification clicks. (NEO-75240)
* Fixed errors in cleanup workflows for deliveries with external cancel-pending statuses. The database record retrieval logic has been corrected. (NEO-74833)
* Resolved a timezone discrepancy issue in Russia (UTC+3:00 Moscow) where `nlserver` output times were incorrect. The time synchronization logic has been updated. (NEO-74754)
* Fixed errors in the `defaultMidSourcingDlvStat` workflow caused by incorrect SQL syntax for MSSQL databases. The query generation logic has been adjusted for compatibility. (NEO-74156)
* Addressed multiple crashes in the web process. (NEO-73174)
* Fixed an issue with BigQuery queries failing when apostrophes were present in conditions. The query handling logic has been updated to correctly interpret special characters. (NEO-72547)
* Resolved an issue where typology rules with exclusion filters were not working correctly. The SQL query generation for delivery preparation has been fixed. (NEO-72292)
* Addressed discrepancies in event dates and contact dates for bounce management. The timezone handling logic has been improved. (NEO-72277)
* Enhanced handling of incorrectly converted UTF-8 characters in direct mail deliveries. Hidden characters are now correctly processed to prevent delivery failures. (NEO-72148)
* Fixed errors in the Inbound SMS activity where filters caused saving issues. The workflow now saves correctly without generating errors. (NEO-70427)
* Corrected SQL query generation for grouped eligibility criteria in offer spaces. Missing parenthesis in SQL conditions have been added to ensure proper filtering. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Fixed intermittent errors in BigQuery data loading workflows caused by HTTP content or transfer encoding issues. The connection handling logic has been improved. (NEO-66989)

