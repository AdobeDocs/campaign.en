---
product: Adobe Campaign
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: yes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
---
# Latest release{#latest-release}

This page lists new capabilities, improvements and fixes coming with the **latest Campaign v8 Release**.

## Release 8.1.2 - Build 9335 {#release-8-1-2-build-9335}

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
<p>The new <b>Change Data Source</b> activity allows you to change the data source of a workflow working table. This provides enhanced flexibility in managing data accross different data sources (FDA, FFDA & local database).</p>
<p>In Adobe Campaign workflows, data is managed using working (or temporary) tables. As the workflow executes, working tables share data accross workflow activities. By default, working tables are created on the same database as the source of the data we query on.</p>
<p>With Campaign v8, the main profiles table is stored on the cloud database directly. So querying on the Profiles table will create a working table on the cloud database as well. In certain cases, it can make sense to move the working table to another data source in order to perform specific operations.</p>
</p>
<p>For more information refer to the <a href="../../delivery/using/line-channel.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE channel enhancements</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>The following improvements have been added to LINE channel when used with Message Center:
</p>
<ul> 
<li><p>Fixed an issue which could prevent visitors from being targeted in a LINE delivery. 
</p></li>
<li><p>Fixed an issue which could cause errors when retrieving visitors from the execution instance to the marketing instance.
</p></li>
<li><p>Fixed issues during the processing of real-time events in the context of LINE deliveries using Message Center.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Other improvements**

* Fixed an issue which could prevent the **Hot clicks** report from displaying for specific deliveries.
* Fixed an issue with the **Deduplication** workflow activity which could result in an inacurrate duplicate counting.
* Fixed an issue when using a workflow query with the "ID is not empty" filter which could result in an empty item being dislayed in the transition population.
* Fixed an issue which prevented additional fields from being created in a new target mapping.
