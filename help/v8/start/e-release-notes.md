---
title: Early Campaign v8 release notes
description: Early Campaign v8 release
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: yes
hidefromtoc: yes
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
---
# Early release notes {#e-new-release}

This page describes improvements and fixes included in the next Campaign v8 release. This content is subject to changes without prior notice until the release date. The official release notes are available in this [page](../start/release-notes.md).

## Release 8.5 {#release-8-5}

_June 30, 2023_

**What's new?**

<table> 
<thead>
<tr> 
<th> <strong>Enhanced Push notification service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5 is introducing our latest Push notification service on v8, powered by a robust framework built on a modern cutting-edge technology. This service is designed to unlock new levels of scalability, ensuring that your notifications can reach a larger audience with seamless efficiency. With our enhanced infrastructure and optimized processes, you can expect higher scale and reliability, empowering you to engage and connect with your Mobile App users like never before. This capability is only available for a selected group of customers (Limited Availability).</p>
</td> 
</tr> 
</tbody> 
</table>

**Compatibility updates**

* The 32-bit version of the Client Console is now deprecated. Starting 8.6, the Client Console will only be available in 64-bits. The upgrade to the 64-bit version of the Client Console is seamless. For more information on how to upgrade your operating system, refer to this [technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html).
* You can now connect your Campaign v8 instance to your Azure Synapse external database. This connection is managed through a new external account.

**Improvements**

* SMS throughput has been significantly enhanced by implementing a range of optimizations, resulting in improved speed and efficiency for SMS communication.
* Starting Campaign v8.5, the authentication process to Campaign v8 has been improved. Technical operators must use Adobe Identity Management System (IMS) to connect to Campaign.
* You can now leverage Destination and Source connections to sync profile attributes such as opt-out data between Adobe Experience Platform and Campaign v8 database
* Delivery preparation has been optimized.
* A new key-based authentication option has been added for SFTP external account, alongside the existing user/password authentication method. Users can now securely authenticate using a private key, enhancing security and providing an alternative authentication mechanism for SFTP access.

**Security enhancements**

* You can no longer create operators from the Client Console. You now need to use the Admin Console. [Learn more](../start/gs-permissions.md).
* Several third-party tools have been updated to optimize security.

**Patches**

* Fixed an issue which could lead to special characters in the HTML content of a delivery being incorrectly encoded in several browsers. (NEO-60081)
* Fixed an issue which could prevent you from to saving a report on a Campaign v8 Enterprise (FFDA) deployment. (NEO-56836)
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