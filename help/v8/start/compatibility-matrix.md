---
title: Campaign v8 compatibility matrix
description: Discover systems and versions compatible with Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
---
# Campaign v8 compatibility matrix

This document lists all systems and components supported for the latest build of **Adobe Campaign v8**. Unless mentioned otherwise, all minor releases are supported. Products and versions that are not part of this list are not compatible with Adobe Campaign.

As specific versions of these 3rd party systems and tools reach end-of-life (EOL), Adobe Campaign will no longer be compatible with those versions, and they will be removed from this compatibility matrix. Please ensure you are on supported versions of any systems listed in the compatibility matrix to avoid any issues.

>[!NOTE]
>
>Adobe Campaign Server and Client Console must be on the same version. [Learn how to check your version](#version).

## Client Console{#ClientConsoleoperatingsystems}

The following operating systems and browser are required to use Campaign Client Console. [Learn more](connect.md).

>[!NOTE]
>
>Please note that the 32-bit version of the Client Console is deprecated starting 8.5 release. Starting 8.6, the Client Console will only be available in 64-bits. For more information on how to upgrade your operating system, refer to this [technote](../../technotes/upgrades/console.md).

### Operating systems{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

### Web browser{#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, latest version. Download it from [Microsoft Developer site](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}.

## CRM connectors{#CRMconnectors}

Customer Relationship Management (CRM) systems compatible with Adobe Campaign are listed below. [Learn more](../connect/crm.md).

* **Salesforce** connector API version 49
* **Microsoft Dynamics** connector, Web API: Dynamics 365 on-premise and online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

External databases compatible with Adobe Campaign Federated Data Access (FDA) module are listed below. [Learn more](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobile SDK{#MobileSDK}

To send [push notifications](../send/push.md) with Campaign, use the Adobe Experience Platform Mobile SDK by configuring the Adobe Campaign Classic extension in the Data Collection UI. 


## Web access{#web-access}

The following browsers are compatible with Campaign for [Web Access](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (latest versions)

## How to check your Campaign version and build{#version}

Access the **Help > About…** menu to check your version.

![](assets/ac-version.png)

You access the following information:

* The **version** number of your Client Console and Application server. In the sample above, the version is 8.1.5 for both the Client Console and the Application server.
* The SHA number, between parenthesis.
* A link to contact Adobe Customer Care.
* Links to Adobe Privacy Policy, Terms of Use and Cookies Policy.
