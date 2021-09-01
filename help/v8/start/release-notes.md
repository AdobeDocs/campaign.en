---
product: Adobe Campaign
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: no
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
---
# Latest release{#latest-release}

This page lists new capabilities, improvements and fixes coming with the **latest Campaign v8 Release**.

## Release 8.1.19 {#release-8-1-19}

_September 2, 2021_

**Security enhancements**

* Fixed a security issue to reinforce protection against directory traversal attacks. (NEO-28547)

**Improvements**

* Following its end of life, Flash has been removed from all related Campaign features and components, and replaced with HTML5. The **Gauge** type of chart has been removed. (NEO-30330) [Read more](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* When installing the client console on Windows, the installer now checks if there is a parent registry node and creates one if it is missing. This prevents potential issues when launching the console. (NEO-34854)
* The tracking signature feature has been improved to prevent errors linked to the way third-party tools (email clients, internet browsers, etc.) handle special characters. URL parameters are now encoded.

**Other changes**

* Previously deprecated Microsoft CRM connectors (Office 365 and On-premise deployments) have been removed from the interface. [Read more](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* Following the migration to Tomcat 8, the IIS setup script has been updated to fix IIS integration issues. (NEO-31019)
* A guardrail has been added to only allow the [billing technical workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report) to run on the marketing instance.
* The data source identification has been improved in the data and schema tabs of the workflow transitions' **View population** window.
* Missing database indexes were added to the following schemas to prevent database update issues: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Patches**

* Fixed an issue which prevented the **Hot clicks** report from working when offers were linked to the delivery. (NEO-26295)
* Fixed an issue with the **Sub-worfklow** activity when its execution did not generate an output table. (NEO-36242)
* Fixed various issues when exporting the **Descriptive analysis** report to PDF. (NEO-25847)
* Fixed an issue which could lead to deliveries failing when using an external mail delivery. (NEO-37435)
* Fixed an error when connecting to Microsoft CRM using web API. The error message has been removed since functionalities were not impacted.
* Fixed a tracking log deduplication issue when the mid server was set as a relay between tracking and marketing servers. (NEO-36285)
* Fixed a regression which prevented Vault from being used as a specific code store.
* Fixed an issue which prevented you from using variables in an **Enrichment** workflow activity when the incoming transition was from an FDA data source.
* Fixed an issue with FFDA preventing the proper replication of operator groups and rights.
* Fixed an issue which could result in sending an incorrect unsubscription link through the delivery. 
* Fixed an issue in replication management impacting the duration of the postupgrade.
* Fixed an issue which could prevent the **Hot click** from displaying.
* Fixed an issue that could lead to broken URLs in email messages.

## Release 8.1.14 {#release-8-1-14}

_July 23, 2021_

**What's new?**

<table>
<thead>
<tr>
<th><strong>New workflow activity: Change Data Source</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The new <b>Change Data Source</b> workflow activity allows you to change the data source of a workflow's working table. This provides enhanced flexibility in managing data across different data sources (FDA, FFDA & local database).</p>
<p>In Adobe Campaign workflows, data is managed using working (or temporary) tables. As the workflow executes, working tables share data across workflow activities. By default, working tables are created on the same database as the source of the data we query on.</p>
<p>With Campaign v8, the main profiles table is stored on the cloud database directly. So querying on the Profiles table will create a working table on the cloud database as well. In certain cases, it can make sense to move the working table to another data source in order to perform specific operations.</p>
<p>For more information, refer to the <a href="../config/workflows.md#change-data-source-activity">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE channel availability</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The <a href="../send/line.md">LINE channel</a> is now available with Campaign v8, including the following enhancements when combined with the <a href="../send/transactional.md">transactional messaging</a> module:
<ul> 
<li><p>Fixed an issue which could prevent visitors from being targeted in a LINE delivery. 
</p></li>
<li><p>Fixed an issue which could cause errors when retrieving visitors from the execution instance to the marketing instance.
</p></li>
<li><p>Fixed issues during the processing of real-time events.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Other improvements**

* Fixed an issue which could prevent the **Hot clicks** report from displaying for specific deliveries.
* Fixed an issue with the **Deduplication** workflow activity which could result in an inaccurate duplicate counting. 
* Fixed an issue when using a workflow query with the "ID is not empty" filter which could result in an empty item being displayed in the transition population.
* Fixed an issue which prevented additional fields from being created in a new target mapping.
