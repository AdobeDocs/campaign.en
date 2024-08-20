---
title: Campaign v8 compatibility matrix
description: Discover systems and versions compatible with Campaign v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
---
# Campaign v8 compatibility matrix {#compat-matrix}

This document lists all systems and components supported for the latest build of **Adobe Campaign v8** client console. Unless mentioned otherwise, all minor releases are supported. Products and versions that are not part of this list are not compatible with Adobe Campaign.

As specific versions of these 3rd party systems and tools reach end-of-life (EOL), Adobe Campaign will no longer be compatible with those versions, and they will be removed from this compatibility matrix. Please ensure you are on supported versions of any systems listed in the compatibility matrix to avoid any issues.

>[!NOTE]
>
>Adobe Campaign server and Campaign client console must be on the same version. [Learn how to check your version](upgrades.md#version).

## Client console {#ClientConsoleoperatingsystems}

The following operating systems and browser are required to use Campaign client console. [Learn more](connect.md).

### Operating systems {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>The 32-bit version of the client console is deprecated since 8.5 release. Starting 8.6, the client console is only available in 64-bits. For more information on how to upgrade your system, refer to this [technote](../../technotes/upgrades/console.md).

### Web browser {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, latest version. Download it from [Microsoft Developer site](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}.

## CRM connectors {#CRMconnectors}

Customer Relationship Management (CRM) systems compatible with Adobe Campaign are listed below. Learn more about CRM connectors [in this page](../connect/crm.md).

* **Salesforce** connector API version 49
* **Microsoft Dynamics** connector, Web API: Dynamics 365 on-premise and online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

External databases compatible with Adobe Campaign Federated Data Access (FDA) module are listed below. Learn more about FDA [in this page](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, starting Campaign v8.5
* **[!DNL Databricks]**, starting Campaign v8.7
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**


>[!AVAILABILITY]
>In addition, with the [Enhanced Security Add-on](../config/enhanced-security.md#secure-vpn-tunneling), you can access your on-premise databases, through the secure VPN tunelling. [Learn more](../config/enhanced-security.md#vpn-callouts)

## Mobile SDK {#MobileSDK}

To send [push notifications](../send/push.md) with Campaign, use the Adobe Experience Platform Mobile SDK by configuring the Adobe Campaign Classic extension in the Data Collection UI. 

Compatible versions for iOS and Android are detailed in the [Adobe Developer documentation](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Web user interface {#web-ui}

The following browsers are compatible with Campaign Web User Interface. Learn more about Campaign Web UI [in this page](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (latest versions)

## Web access {#web-access}

The following browsers are compatible with Campaign for Web Access. Learn more about Campaign Web access [in this page](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (latest versions)

## Additional resources {#support}

* [Campaign Release updates](upgrades.md)
* [Check your Campaign version](upgrades.md#version)
* [Install Campaign client console](connect.md)
* [Control Panel releases](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}

To be informed of new Experience Cloud solution releases, subscribe to the [Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html){target="_blank"}.