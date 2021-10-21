---
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

## Release 8.2.1 {#release-8-2-1}

_October 25, 2021_

<table>
<thead>
<tr>
<th><strong>Inbound Interaction</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-time interaction management is now available for inboud channels. Use Campaign Inbound Interaction module to present the best offer to your customers as they visit your website or reach out to your call center. This capability comes with Campaign v8 as an option and requires specific configuration on your instance. Reach out to your Adobe representative to have access to the Inbound Interaction module.</p>
<p>For more information, refer to the <a href="../send/interaction-architecture.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Campaign Optimization</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign Optimization module is now available. This module lets you control, filter and monitor the sending of deliveries. To avoid conflicts between campaigns, Adobe Campaign can test various combinations by applying specific constraint rules. This guarantees that the messages sent meet the needs and expectations of customers and company communication policies.</p>
<p>For more information, refer to the related <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html">Campaign Classic v7 documentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service is a new Cloud Database Manager component. It helps users preserve and monitor the integrity of unique key constraints within Cloud Database tables. This allows you to reduce the risk of inserting duplicate keys.
</td> 
</tr> 
</tbody> 
</table>

**Improvements**

* The Snowflake connector has been improved in terms of performance.
* In the server configuration file (serverConf.xml), you can now set a wait time, per schema, between updates and commit replications on the fly.
* For monitoring and testing purposes, the audit logs of the **[!UICONTROL Replicate Staging data]** workflow now include the number of records that have been sent to the FFDA (Full Federated Data Access) database.
* The SQL code activity now allows you to choose in which database the SQL script will be stored: the default data source or a chosen active FDA external account.
* A set of predefined warehouses is now available and can be used to run various queries in parallel such as segmentation, ETL or peaks.

**Other changes**

* The **[!UICONTROL Encrypted identifier]** field has been added to the visitor schema (`nms:visitor`). This field is calculated and is to be used for web applications.
* Fixed an issue that caused the delivery analysis to fail when some IP affinities existed in some mid-sourcing containers but not in all of them. Now the IP affinities are all stored in the database, so that any container can access the affinities present in all the other containers. (NEO-37564)
* You can now import a package with multiple schemas and navigation tree nodes.

**Patches**

* After a user had removed, in a data schema, the `<autoStg>` attribute from a table definition element, or changed its value from `true` to `false`, the related staging table was not deleted. This issue has been fixed.
* Fixed an issue that caused an error when creating records with a dedicated form due to Id management with an FFDA datasource.
* Fixed an issue that could prevent offers from being inserted into a delivery if the offers were managed by an enrichment activity in a workflow.
* Fixed an issue that could slow down the import of packages.
* Fixed an issue that could prevent email deliveries with seed addresses from being sent.
* Fixed an issue that could prevent propositions from being saved in the offer propositions table.
* Fixed an issue that caused network timeout issues to be incorrectly logged as script interruption issues instead of network errors. This issue occurred in the case of HTTP requests that were included in JavaScript activities.
* Fixed an issue that prevented offers from being replicated to the live offer environment on Snowflake.
* Fixed an issue that ignored the 'autoStg' attribute for non-extended built-in schemas.
* Fixed an issue that prevented users from selecting the **[!UICONTROL Country/Region]** link when previewing a profile.
* Fixed an issue that caused the datepicker in custom reports to result in a script error. (NEO-36345)
* Fixed an issue that caused the system to crash when regenerating configuration in case of bad configuration files.
* Fixed an issue that prevented the marketing and the control instances from being successfully upgraded.
* Fixed an issue that could cause the billing workflow to crash on marketing instances.
* Fixed an issue that could lead to duplicate keys in FFDA Snowflake out-of-the-box tables. (NEO-38583)
* Fixed an issue which could lead to workflow temporary schemas being lost when editing two deduplication activities one after the other. (NEO-34063)
* Fixed an issue that returned incorrect results when running the Amazon Redshift HoursDiff and MinutesDiff functions while trying to extract the time component.(NEO-31673)
* Fixed an issue which could prevent users from login to the console due to a proxy configuration issue. (NEO-38388)
* Fixed a regression issue which prevented the **Purge folder** functionality from working correctly. (NEO-37459)
* Fixed an issue that could prevent you from previewing mobile deliveries that were attached to a workflow.
* Fixed an issue which could prevent the **Read list** workflow activity from working when the list was identified in the database with a negative ID. (NEO-39607)

## Release 8.1.20 {#release-8-1-20}

_September 7, 2021_

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
