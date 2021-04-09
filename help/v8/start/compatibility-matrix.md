---
solution: Campaign Classic
product: campaign
title: Campaign v8 compatibility matrix
description: Learn systems and versions compatible with Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
---
# Campaign v8 compatibility matrix

This document lists all systems and components supported for [the latest build](release-notes.md) of **Adobe Campaign v8**. Products and versions that are not part of this list are not compatible with Adobe Campaign.

>[!CAUTION]
>
>* Unless mentioned otherwise, all minor releases are supported.
>* As specific versions of these 3rd party systems and tools reach end-of-life (EOL), Adobe Campaign will no longer be compatible with those versions, and they will be removed from this compatibility matrix. Please ensure you are on supported versions of any systems listed in the compatibility matrix to avoid any issues.

## Compatible systems

### CRM connectors{#CRMconnectors}

<table>
<tbody>
<tr>
<td>Salesforce connector API</td>
<td>
<p>API version 49</p>
</td>
</tr>
<tr>
<td>Microsoft Dynamics connector</td>
<td>
<p>Web API: Dynamics 365 On-premise and Online</p>
</td>
</tr>
</tbody>
</table>

### Federated Data Access (FDA){#FederatedDataAccessFDA}

<table>
<tbody>
<tr>
<td>Microsoft Azure Synapse Analytics</td>
<td>&nbsp;</td>
</tr>
<tr>
<td>Amazon Redshift</td>
<td><p>&nbsp;</p>
</td>
</tr>
<tr>
<td>Oracle</td>
<td>
<p>19c</p>
<p>18c</p>
<p>12c</p>
<p>11g</p>
</td>
</tr>
<tr>
<td>PostgreSQL</td>
<td>
<p>12.x</p>
<p>11.x</p>
<p>10.x</p>
<p>9.6.x</p>
<p>9.5.x</p>
<p>9.4.x</p>
</td>
</tr>
<tr><td>SQL Server</td>
<td>
<p>2019</p>
<p>2017</p>
<p>2016</p>
<p>2014</p>
<p>2012 SP1 and SP2</p>
</td>
</tr>
<tr><td>MySQL</td>
<td>
<p>5.7</p>
</td>
</tr>
<tr>
<td>Teradata</td>
<td>
<p>16.20</p>
<p>16</p>
<p>15.10</p>
<p>15.0</p>
</td>
</tr>
<tr>
<td>Netezza</td>
<td>
<p>7.2</p>
</td>
</tr>
<tr>
<td>Sybase</td>
<td>
<p>IQ 16</p>
<p>ASE 15.7</p>
</td>
</tr>
<tr>
<td>SAP HANA</td>
<td>
<p>version 1 SPS 12</p>
</td>
</tr>
<tr><td>Hadoop via HiveSQL</td>
<td>
<p>HortonWorks HDP 2.4.X, 2.5.x, 2.6.x</p>
<p>HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6)</p>
<p>Cloudera CDH6.x</p>
</td>
</tr>
<tr>
<td>Snowflake</td>
<td>&nbsp;</td>
</tr>
</tbody>
</table>

### Client Console operating systems{#ClientConsoleoperatingsystems}

<table>
<tbody>
<tr>
<td>Windows Server</td>
<td>
<p>2016</p>
<p>2012</p>
</td>
</tr>
<tr>
<td>Windows</td>
<td>
<p>8</p>
<p>10 (recommended for Japanese instances)</p>
</td>
</tr>
</tbody>
</table>

### Mobile SDK{#MobileSDK}

<table>
<tbody>
<tr>
<td>Android</td>
<td>
<p>7.x, 8.x, 9.0</p>
<p>with mobile SDK build 1.0.27.</p>
</td>
</tr>
<tr>
<td>iOS</td>
<td>
<p>iOS 9 - 14</p>
<p>with mobile SDK build 1.0.26, compatible with 32 and 64-bit versions.</p>
</td>
</tr>
</tbody>
</table>

## Supported browsers {#Browsers}

For the following browsers, the latest version is supported: Microsoft Edge, Mozilla Firefox, Google Chrome, Safari.

Internet Explorer 11 is supported.

## How to check your Campaign version

The **Help > About…** menu lets you access the following information:

* the version number for Campaign client console and application server
* the build number for Campaign client console and application server
* a link to contact Adobe Customer Care
* links to Adobe Privacy Policy, Terms of Use and Cookies Policy
