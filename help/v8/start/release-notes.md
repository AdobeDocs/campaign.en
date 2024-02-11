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

As a Managed Cloud Services user, your instance is upgraded by Adobe with every new release. Adobe will contact you and upgrade your environments. Campaign Client Console **must be upgraded to the same version** as Campaign servers. Learn how to upgrade your Client Console in this [page](../start/connect.md#upgrade-ac-console). 

In addition, as a customer, ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).

## Release 8.5.2 {#release-8-5-2}

_Aug 2, 2023_

Fixed a security issue which could occur when upgrading to 8.5.1. (NEO-64767)

## Release 8.5.1 {#release-8-5}

_June 30, 2023_


**Enhanced Push notification service**

Campaign v8.5.1 is introducing our latest Push notification service, powered by a robust framework built on a modern cutting-edge technology. This service is designed to unlock new levels of scalability, ensuring that your notifications can reach a larger audience with seamless efficiency. With our enhanced infrastructure and optimized processes, you can expect higher scale and reliability, empowering you to engage and connect with your Mobile App users like never before. This capability is only available for a selected group of customers (Limited Availability).

For more information, refer to the [detailed documentation](../send/push-data-collection.md).



<!--
The newly introduced Push notification service showcases significant improvements in throughput for both Push Android and Push iOS compared to our previous version (v8.4). Users will experience notably enhanced performance with the upgraded service in the latest version (v8.5).

* Push Notifications (Android): up to **5x** faster
* Push Notifications (iOS): up to **2.2x** faster

SMS throughput has undergone substantial enhancements through a series of optimizations, resulting in notable improvements in speed and efficiency for SMS communication. These upgrades have led to increased throughput from the previous version (v8.4) to the latest version (v8.5), encompassing both sending and feedback updates. Users can now experience the benefits of this enhanced SMS service.</p>

* SMS throughput: up to **5x** faster

These max throughput performances have been measured by Adobe testing teams, in lab conditions.
-->

<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="Throughput improvements" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>
<p><strong>Mobile channel increased throughputs</strong></p>
<p>The newly introduced Push notification service showcases significant improvements in throughput for both Push Android and Push iOS compared to our previous version (v8.4). Users will experience notably enhanced performance with the upgraded service in the latest version (v8.5). </p>
<ul>
<li>Push Notifications (Android): up to <strong>5x</strong> faster </li>
<li>Push Notifications (iOS): up to <strong>2.2x</strong> faster</li>
</ul>
<p>SMS throughput has undergone substantial enhancements through a series of optimizations, resulting in notable improvements in speed and efficiency for SMS communication. These upgrades have led to increased throughput from the previous version (v8.4) to the latest version (v8.5), encompassing both sending and feedback updates. Users can now experience the benefits of this enhanced SMS service.</p>
<ul>
<li>SMS throughput: up to <strong>5x</strong> faster</li>
</ul>
<p><em>These max throughput performances have been measured by Adobe testing teams, in lab conditions.</em></p>
</div>
<p></p>
</td>
</tr></table>


**General improvements**

* You can now leverage Adobe Experience Platform Destination connection to sync profile attributes such as opt-out data between Adobe Experience Platform and Campaign v8 database. 
* Delivery preparation has been optimized, across all channels.
* A new key-based authentication option has been added for the SFTP external account, alongside the existing user/password authentication method. Users can now securely authenticate using a private key, enhancing security and providing an alternative authentication mechanism for SFTP access. Learn more in [this section](../config/external-accounts.md).

**Security enhancements**

* With Campaign v8.5.1, the authentication process to Campaign v8 has been improved and secured. Technical operators must now use Adobe Identity Management System (IMS) to connect to Campaign. Learn how to migrate your existing technical account(s) in [this technote](../../technotes/upgrades/ims-migration.md).
* Starting the upcoming v8.6, you will no longer be allowed to create operators from Campaign Client Console. If you are using the login/password native authentication, you must migrate your operators to Adobe Identity Management System (IMS). Learn how to migrate your operators in [this technote](../../technotes/upgrades/migrate-users-to-ims.md).
* Several third-party tools have been updated to optimize security.

**Compatibility updates**

* The 32-bit version of the Client Console is now deprecated. Starting 8.6, the Client Console will only be available in 64-bits. The upgrade to the 64-bit version of the Client Console is seamless. For more information on how to upgrade your operating system, refer to this [technote](../../technotes/upgrades/console.md).
* You can now connect your Campaign v8 instance to your Azure Synapse external database. This connection is managed through a new external account. Learn more in [Campaign compatibility matrix](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


**Patches**

* Fixed an issue which could lead to special characters in the HTML content of a delivery being incorrectly encoded in several browsers. (NEO-60081)
* Fixed an issue which could prevent you from saving a report on a Campaign v8 Enterprise (FFDA) deployment. (NEO-56836)
* Fixed an issue when inserting or updating data into a custom FFDA schema via an Update Data workflow activity. (NEO-54708)
* Fixed an issue which prevented the database cleanup workflow from removing addresses in the nms:address table on FFDA. (NEO-54460)
* Fixed an issue with the billing workflow which could fail with a "Compilation memory exhausted" error. (NEO-51137)
* Fixed an issue which could prevent the GPG decryption from working correctly in the Data loading (file) workflow activity. (NEO-50257)
* Fixed an issue which prevented the `JSPContext.sqlExecWithOneParam` function from working. (NEO-50066)
* Fixed an issue which led to delivery failures when using non-printable characters in personalization fields. (NEO-48588)
* Fixed an issue which could cause delivery errors when inserting Adobe Target dynamic images. (NEO-62689)
* Fixed an issue to prevent browsers from adding extra spaces when using conditional content in a delivery. (NEO-62132)
* Fixed an issue which caused a popup window to open when clicking on an image in the email content editor. (NEO-60752)
* Fixed an issue which could lead to an error and prevent you from scrolling when editing the content of a delivery. (NEO-61364)
* Adobe Analytics connector now exports the metrics with the correct channel type. It was previously always set as 'email' channel. (NEO-26340)
* Fixed an issue which could lead to errors when using the Big Query connector with datetime fields. (NEO-49768)


## Release 8.4.5 {#release-8-4-5}

_April 3, 2023_

**Patches**

* Fixed an issue which could lead to a duplicate key constraint error if several approval workflows were set to the same schedule. (NEO-48968)
* Fixed a regression issue introduced by NEO-54474 (8.4.4) which led the style attribute of the body tag to be changed when uploading an image in the Digital Content Editor (DCE). (NEO-57697) 
* Fixed an issue which could lead to an error when exporting data using a CRM connector if the temporary table had a primary key defined as long instead of uuid. (NEO-54153)
* Fixed a regression issue introduced in 8.4.1 which could lead to errors in package export, FDA over HTTP and reporting. (NEO-57731)
* Fixed a regression issue introduced in 8.3.8 which could prevent the delivery status from being correctly updated for deliveries with negative IDs. (NEO-54675)
* Fixed an issue with boolean fields when importing data using the Big Query connector (NEO-49181)


## Release 8.4.4 {#release-8-4-4}

_March 8, 2023_

**Security enhancement**

* To improve security, Tomcat has been updated from version 8.5.81 to 8.5.85. (NEO-50530)

**Patches**

* Fixed an issue which could prevent you from scrolling in the **Edit** tab of the Digital Content Editor (DCE). (NEO-54474)
* Fixed an issue during replication which could lead to a web server crash. (NEO-53670)


## Release 8.4.3 {#release-8-4-3}


_January 27, 2023_

**Improvements**

* Fixed a delivery indicator synchronization issue between the marketing server and the mid-sourcing server. (NEO-50724) <!--OKKKK-->
* Fixed an issue which could lead to an error when exporting a workflow. (NEO-50555) <!--OKKKK-->
* Fixed an issue when extending a schema that was previously extended. (NEO-49118) <!--OKKKK-->
* Fixed an issue when using two enrichment activities with the same identifier in the link definition. (NEO-48851) 
* Fixed two delivery preparation failure issues. Delivery preparation could fail when the number of potential offers being manipulated was too high. The second issue occurred when the image URLs were defined as URLs to track in a text format delivery. (NEO-48807) <!--OKKKK-->
* Fixed an issue which could lead to a workflow failure where a workflow would overwrite the warehouse name defined in the external account for non-FFDA accounts. (NEO-43209) <!--OKKKK-->
* Improved security on web applications to prevent DDoS attacks. (NEO-50757) <!--OKKKK-->
* The management of consolidated tracking data has been improved in the **[!UICONTROL Consolidated tracking]** (nms:trackingStats) FFDA table to avoid duplicates. (NEO-46409)
* Fixed a logical operator issue in workflow queries when using an `enableIf` in a logical operator condition. The previous logical condition was overwritten. (NEO-45815)  <!--OKKKK-->
* The generation of active profiles has been optimized in the billing workflow to improve performance. (NEO-47658) <!--OKKKK-->
* Fixed an issue with HTML file import when image nodes (img) contained URLs with personalization fields. (NEO-48396)
* Fixed an issue with Snowflake (all deployments) when using the sorting parameter in a **Split** workflow activity. (NEO-45899) <!--OKKKK-->
* Fixed an issue that led to an error when a user with read access rights on the nmsDeliveryMapping folder tried to run a campaign or workflow. (NEO-48230)
* Fixed a performance issue in the HTML tab of a delivery which could occur for large HTML code. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Fixed an issue which prevented users from using the **Merge selected lines** workflow option. (NEO-48488)
* Fixed an issue on Snowflake FDA connector which led to records being dropped when using the "0 or 1 cardinality simple join" option during enrichment. (NEO-48737)
* The remaining references to the log4j library have been removed from the Campaign installation on Windows. (NEO-44851)
* Fixed an issue which could lead to an error when adding the **Recipients who have opened**  (estimatedRecipientOpen) indicator in the additional data of a **Query** workflow activity. (NEO-46665)
* The management of tracking URLs has been improved in workflows with multiple deliveries to improve performance. (NEO-50894) <!--OKKKK-->
* Fixed an issue which could cause the replication of schemas that uses Xtkfolder to fail. (NEO-46787) <!--OKKKK-->
* Fixed an issue cause could cause the "lastModified" custom column to be dropped in the NmsSubscription table. (NEO-48402)


