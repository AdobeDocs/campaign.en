---
title: Early Campaign v8 release notes
description: Early Campaign v8 release
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: yes
hidefromtoc: yes

---
# Early release notes {#e-new-release}

This page describes improvements and fixes included in the next Campaign v8 release.

>[!CAUTION]
>
> This content is subject to changes without prior notice until the release date. The official release notes are available in this [page](../start/release-notes.md).

## Release 8.3.9 {#release-8-3-9}

_October 7, 2022_

**Patches**

* Fixed an issue which impacted the Delivery log status updates on the MID instance, when the FeatureFlag_GZIP_Compression option was enabled. (NEO-49183)
* The clean up workflow now also handles custom staging schemas. (NEO-48974)
* Fixed an issue which could lead deliveries to stay in **Pending** status even if the contact date was reached. (NEO-48079, NEO-48251)
* Improved stability when handling invalid XML strings during SOAP calls. (NEO-48027)
* Fixed an issue which could slow down the delivery analysis, during the exclusion of denylisted recipients step, when targeting large volumes of recipients. (NEO-48019)
* To prevent slowness when sending proof to seed addresses, all consecutive replications of seed members are now grouped into one replication request. (NEO-44844)
* Fixed an issue which led to personalization issues when sending SMS messages using an external delivery mode. (NEO-46415)
* Fixed an issue which displayed an error when trying to preview a delivery in any Message Center archived event. (NEO-43620)
* Fixed an issue in workflows which could prevent files from being updated on server when using the **Data loading (file)** activity. The process stopped at 100% but never ended. (NEO-47269)
* Fixed an issue which led to the creation of unnecessary DeliveryParts when the delivery was using calendar and split modes. (NEO-48634)
* Fixed a performance issue when using calendar-based waves. (NEO-48451)
* Fixed an issue which could lead to an error message in the delivery list screen after creating a new target mapping on a custom schema. (NEO-49237)
* Fixed an issue that could occur if a delivery reached a specific size during MTA process. (NEO-46097)
* Fixed an issue which prevented tracking logs from returning data related to the recipient’s browser. (NEO-46612)
* Fixed an issue during postupgrade on Japanese environments. (NEO-46640)
* Fixed an issue when using the **Query** activity and filtering a table. When a column name contained the word “Update”, a compilation error occured with an invalid identifier and the following message: "number of rows updated". (NEO-46485)
* Fixed an issue which prevented the **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) technical workflow from stopping even when an error occurred during its execution. (NEO-46280)
* Fixed an issue which could cause data loss if the staging workflow was in error and the retention period fully passed. (NEO-48975)
* Fixed an issue when injecting data into Snowflake cloud database with a Campaign **Query** activity and a **Change Data Source** activity: the process was failing when a backslash character is present in the data. The source string was not escaped, and data was not processed correctly on Snowflake. (NEO-45549)
