---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: no
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest release{#latest-release}

This page lists new capabilities, improvements and fixes coming with the **latest Campaign v8 Release**.

## Release 8.4.4 {#release-8-4-4}

>[!CAUTION]
>
> Client Console upgrade is mandatory. Learn how to upgrade your Client Console in this [page](../start/connect.md#download-ac-console). 

_March 8, 2023_

**Security enhancement**

* To improve security, Tomcat has been updated from version 8.5.81 to 8.5.85. (NEO-50530)

**Patches**

* Fixed an issue which could prevent you from scrolling in the **Edit** tab of the Digital Content Editor (DCE). (NEO-54474)
* Fixed an issue during replication which could lead to a web server crash. (NEO-53670)

## Release 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> Client Console upgrade is mandatory. Learn how to upgrade your Client Console in this [page](../start/connect.md#download-ac-console). 

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
