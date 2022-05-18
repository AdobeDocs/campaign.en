---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: no
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest release{#latest-release}

This page lists new capabilities, improvements and fixes coming with the **latest Campaign v8 Release**.

## Release 8.3.8 {#release-8-3-8}

_May 18, 2022_

**What's new?**


<table> 
<thead>
<tr> 
<th> <strong>Time Sensitive notifications</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>With iOS 15, Apple added a notion of sensitive notification that gives control to the app developer to bypass Focus mode when a notification is considered as sensitive and then needs to reach the user in real-time.</p>
<p>For more information, refer to the <a href="../send/push.md#send-notifications-on-ios">detailed documentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Core Privacy Service Integration</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 now integrates with Adobe Privacy Core Service. Privacy requests pushed from the Privacy Core Service to all Experience Cloud solutions are automatically handled by Campaign via a dedicated workflow.</p>
<p>For more information, refer to the <a href="privacy.md">detailed documentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table>
<thead>
<tr>
<th><strong>Response Manager</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Campaign Response Management lets you measure the success and ROI of your marketing campaigns or offer propositions across all channels: email, mobile, direct mail, etc.</p>
<p>For more information, refer to the <a href="../start/campaigns.md#response-manager-add-on">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Distributed Marketing</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign Distributed Marketing lets you implement collaborative campaigns between central entities (headquarters, marketing departments, etc.) and local entities (sales points, regional agencies, etc.). Through a shared workspace (campaign packages), you can create campaign templates and propose them to your local entities.</p>
<p>For more information, refer to the <a href="../start/campaigns.md#distributed-marketing-add-on">detailed documentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Compatibility updates**

* Campaign v8 SDK now supports Android 12 and iOS 15 for Push Notifications.
* Campaign v8 is now compatible with Windows 11.

Refer to the [Campaign Compatibility matrix](compatibility-matrix.md).

**Improvements**

* Microsoft Exchange Online OAuth 2.0 authentication for POP3 is now supported in Campaign. [Read more](../config/external-accounts.md#bounce-mails-external-account)
* Critical fixes have been applied regarding the Microsoft Dynamics Connector web API. 
* The new Operator and group schema write (operatorWrite) named right has been added to allow users to insert, update and delete Operators (xtk:operator) and Operator groups (xtk:group) schemas. 
<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* Multiple LINE active accounts can now be configured on a single mid-sourcing.
* The number of default connections for the web process has been increased from 50 to 150. 
* Campaign comes with a set of new guardrails to prevent insertion of duplicated keys in Snowflake database. [Read more](../architecture/keys.md)

**Patches**

* Fixed an issue which occurred when using seeds and control groups in the same recurring delivery. (NEO-41197)
* Fixed an issue on FFDA which led to email sending being blocked for all récipients belonging to the same deliveryPart during the sending process (up to 256) when personalization blocks contained one of the following characters: `' & < > "`. These characters are now supported in personalization blocks (example: firstname="Brian O'Neil"). (NEO-43184)
* Fixed an issue which could lead the tracking workflow to fail when using a custom schema as a target mapping. We now ensure that the type of the foreign link to a custom targeting schema is correct when generating broadLog schema via the target mapping wizard. (NEO-43506) 
* Fixed an issue which could lead the FFDA deployment workflows to fail for languages other than English. (NEO-44561)

## Release 8.2.10 {#release-8-2-10}

_February 2, 2022_

**Patches**

* Fixed an issue which caused the delivery preparation to fail if the maximum number of messages, defined in the typology rule, was reached.
* Fixed an issue during the configuration of the Adobe Analytics connector when the email address contained an "s" character.
* Fixed an issue during postupgrade which could cause the deliveryMapping table to lose data from a custom delivery mapping.
* Fixed an issue which could lead to recipients receiving the same message multiple times for the same delivery when the email address contained a single quote character ('). This character is now escaped. (NEO-41198)
* Fixed an ID generation issue when sending proofs with seeds or substitution addresses. (NEO-42637)
* Fixed an issue which could prevent you from sending proofs using the substitution of address method. (NEO-40417)
* Fixed an issue which prevented you from installing the LINE package. (NEO-42503)

## Release 8.2.8 {#release-8-2-8}

_October 28, 2021_

<table>
<thead>
<tr>
<th><strong>Inbound Interaction</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-time interaction management is now available for inbound channels. Use Campaign Inbound Interaction module to present the best offer to your customers as they visit your website or reach out to your call center. This capability comes with Campaign v8 as an option and requires specific configuration on your instance. Reach out to your Adobe representative to have access to the Inbound Interaction module.</p>
<p>For more information, refer to the <a href="../interaction/interaction-architecture.md">detailed documentation</a>.</p>
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
<p>As Cloud Database does not enforce unicity constraints, Unicity Service introduces at application level, <b>a set of new guardrails</b> reduce the risk of inserting duplicates when managing the data with Adobe Campaign.</p> 
<p>Unicity Service initiates a new built-in workflow called <b>ffdaUnicity</b> to monitor unicity constraints and alert when duplicates are detected.</p>
<p>For more information, refer to the <a href="../architecture/keys.md">detailed documentation</a>.</p>
</td> </tr> 
</tbody> 
</table>

<!--
<table> 
<thead>
<tr> 
<th> <strong>Twitter channel availability</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The <a href="../send/twitter.md">Twitter social channel</a> is now available with Campaign v8. You can:</p>
<ul> 
<li><p>Send messages on Twitter: Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.
</p></li>
<li><p>Collect new contacts: Adobe Campaign can automatically recovers the profile data, which enables you to carry out targeting campaigns and implement cross-channel strategies.
</p></li>
</ul>
<p>Learn how to connect Campaign and Twitter in the <a href="../connect/ac-tw.md">detailed documentation</a>.</p>
<p>Learn how to post tweets and send direct messages with Campaign in <a href="../connect/ac-tw.md">this page</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Improvements**

* The Snowflake connector has been improved in terms of performance.
* For monitoring and testing purposes, the audit logs of the **[!UICONTROL Replicate Staging data]** workflow now include the number of records that have been sent to the FFDA (Full Federated Data Access) database.
* The SQL code activity now allows you to choose in which database the SQL script will be stored: the default data source or a chosen active FDA external account.
* A set of pre-defined warehouses is now available and can be used to run various queries in parallel such as segmentation, ETL or peaks. [Read more](../config/workflows.md)

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
