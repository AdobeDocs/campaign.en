---
product: campaign
title: Latest Release
description: Latest Campaign Classic Release Notes
feature: Overview
role: User
level: Beginner
exl-id: d65869ca-a785-4327-8e8d-791c28e4696c
---
# Latest release{#latest-release}

This page lists new capabilities, improvements and fixes coming with the **latest Campaign v8 Release**.

## Release 8.1.2 - Build ???? {#release-8-1-2-build-????}

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
<p>A new workflow activity is introducted. The <b>Change Data Source</b> activity allows you to change the data source of a workflow working table. This gives you the ability to perform large and efficient unitary operations on working table data by moving the worktable from Snowflake to Postgresql.
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
<li><p>Fixed an issue which could cause errors when when retrieving visitors from the execution instance to the marketing instance.
</p></li>
<li><p>Enrichment during real-time event processing has been enhanced to support the LINE channel.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Other improvements**

* Fixed an issue which could prevent the **Hot clicks** report from displaying when selecting a specific delivery.
* Fixed an issue with the **Deduplication** workflow activity which could result in an inacurrate duplicate counting.
* Fixed an issue when using a workflow query with the "ID is not empty" filter which could result in an empty item being dislayed in the transition population.
* Fixed an issue which prevented additional fields from being created in a new target mapping.
