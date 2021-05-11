---
solution: Campaign
product: Adobe Campaign
title: Campaign v8 compatibility matrix
description: Learn systems and versions compatible with Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
---
# Campaign v8 compatibility matrix

This document lists all systems and components supported for the latest build of **Adobe Campaign v8**. Products and versions that are not part of this list are not compatible with Adobe Campaign.

>[!CAUTION]
>
>* Unless mentioned otherwise, all minor releases are supported.
>* As specific versions of these 3rd party systems and tools reach end-of-life (EOL), Adobe Campaign will no longer be compatible with those versions, and they will be removed from this compatibility matrix. Please ensure you are on supported versions of any systems listed in the compatibility matrix to avoid any issues.

## Compatible systems

### CRM connectors{#CRMconnectors}

* **Salesforce** connector API version 49
* **Microsoft Dynamics** connector, Web API: Dynamics 365 On-premise and Online

### Federated Data Access (FDA){#FederatedDataAccessFDA}
 
* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 and SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza** 7.2
* **Sybase IQ** 16, ASE 15.7
* **SAP HANA** version 1 SPS 12
* **Hadoop** via HiveSQL
    * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
    * HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6
    * Cloudera CDH6.x

### Client Console{#ClientConsoleoperatingsystems}

:warning: The following operating systems and browser are required to use Campaign Client Console.

**Operating systems**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recommended for Japanese instances

**Browser**

Microsoft Internet Explorer 11

### Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 with mobile SDK build 1.0.27.
* **Apple iOS** 9 - 14 with mobile SDK build 1.0.26, compatible with 32 and 64-bit versions.

### Supported browsers {#Browsers}

The following browsers are compatible with Campaign for Web Access.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (latest versions)

* **Internet Explorer** 11

## How to check your Campaign version

The **Help > About…** menu lets you access the following information:

* the version number for Campaign Client Console and application server
* the build number for Campaign Client Console and application server
* a link to contact Adobe Customer Care
* links to Adobe Privacy Policy, Terms of Use and Cookies Policy
