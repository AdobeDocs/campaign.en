---
solution: Campaign Classic
product: campaign
title: Get started with marketing campaigns
description: Get started with marketing campaigns
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
---
# Connect Campaign and other solutions {#gs-ac-connectors}

You can connect your Campaign instance with Adobe Experience Cloud solutions to combine capabilities.

Adobe Campaign comes with several connectors that allow you to communicate with external applications, connect to database engines, share and synchronize data.

Check compatible systems and versions in [this page](compatibility-matrix.md).

## Leverage Adobe solutions {#gs-ac-integration}

Modernize your implementation and leverage all Adobe Experience Cloud capabilities.

:speech_balloon: As a Managed Cloud Service user, [contact Adobe](support.md#support) to connect Campaign with Adobe Experience Cloud services and solutions. You need to implement Adobe Identity Management Service (IMS). [Learn more](connect.md#connect-ims)

Campaign v8 can connect with:

* [Adobe Journey Orchestration](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=en)

* [Real-Time CDP](../connect/ac-rtcdp.md)

* [Adobe Analytics data connector](../connect/ac-aa.md)

* [Adobe Experience Manager](../connect/ac-aem.md)

* [Adobe Target](../connect/ac-at.md)

You can also combine your **audiences** and **assets** across Experience Cloud solutions with Asset sharing and Audience sharing capabilities.

:arrow_upper_right: Learn more about Audience sharing between Campaign and Experience Cloud solutions in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

:arrow_upper_right: Learn more about Asset sharing between Campaign and Experience Cloud solutions in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

## CRM Connectors{#gs-crm-connectors}

You can connect your Adobe Campaign platform to your **CRM third-party systems** and synchronize data: contacts, accounts, purchases, etc. 

Activate your CRM data on cross-channel communication: learn how to pass on contacts from your CRM system to Adobe Campaign, and share campaign data back from Adobe Campaign to your CRM system.
CRM connectors enable quick and easy data integration: Adobe Campaign provides a dedicated wizard for collecting and selecting from the tables available in the CRM. This guarantees two-directional synchronization to make sure data is up-to-date at all times throughout the systems.

Learn how to integrate Campaign with Microsoft Dynamics 365 and Salesforce.com in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-connectors.html).


## Federated Data Access (FDA){#gs-fda}

Use the FDA Connector (Federated Data Access) to connect Campaign to one or more **external databases** and process information stored into them without affecting your Campaign Cloud Database data. you can access external data without changing the structure of Adobe Campaign data.

Campaign FDA option allows you to extend your data model in a third-party database. It will automatically detect the structure of the targeted tables and use data from the SQL sources.

Learn how to **connect Campaign** to an external database in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/configure-fda/config-databases/configure-fda.html)

Specific **permissions** are required on the external database to work with Campaign. [Learn more](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/configure-fda/remote-database-access-rights.html)

Once the data schema is created, data can be processed in Adobe Campaign workflows. For more on this, refer to [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/accessing-an-external-database--fda-.html).

## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages - Use Adobe Campaign Social Marketing to send messages on Twitter. Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts via Facebook: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

:bulb: Learn how to set up and use Campaign Social Marketing in [this section](../connect/ac-tw.md)