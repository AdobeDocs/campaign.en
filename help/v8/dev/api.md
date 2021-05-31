---
solution: Campaign v8
product: Adobe Campaign
title: Get started with Campaign APIs
description: Get started with Campaign APIs
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
---
# Get Started with [!DNL Campaign] APIs{#gs-ac-api}

[!DNL Adobe Campaign] comes with a set of Javascript functions which you can use:

* in Scripts - in [!DNL Adobe Campaign] workflows
* via APIs - from external systems

You can use JavaScript APIs to write in Campaign cloud database or read from the database:

* Business-specific APIs that let you act on each object: deliveries, workflows, subscriptions, and so on. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html).
* Generic data access APIs for querying the data model data. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html).

Campaign v8 works with two databases: a local database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud database for campaign execution, reporting, data ingestion, batch queries and workflow execution.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 comes with a limit on the throughput (TPS) of our API layer. Breaking the limit leads to standard HTTP error (429). As a Managed Cloud Services user, you can contact Adobe to adapt the throttling for each API.
> 

## Prerequisites

Before using [!DNL Adobe Campaign] APIs, you need to be familliar with the following topics:

* JavaScript
* SOAP protocol
* [!DNL Adobe Campaign] datamodel

In order to use APIs and interact with [!DNL Adobe Campaign], you also must be familiar with your data model.  

>[!NOTE]
>You can generate a complete description of your data model. Learn more in [this page](datamodel.md).

## [!DNL Campaign] API staging mechanism

With [!DNL Campaign] Cloud database, blast unitary calls are not recommended due to performance (latency & concurrency). Batch operation is always preferred. In order to guarantee optimal performances of APIs, Campaign keeps handling API calls at the local database level.

[!DNL :bulb:] [API staging mechanism is detailed in this page](staging.md)

## New APIs

New APIs are available to manage data synchronization between [!DNL Campaign] local database and Cloud database. A new mechanism has also been introduced to handle API calls at the local database level to avoid latency and increase the overall performance.

[!DNL :bulb:] [New APIs are detailed in this page](new-apis.md)

**Related topics**

* [Data model best practices](datamodel-best-practices.md)
