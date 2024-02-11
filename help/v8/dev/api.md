---
title: Get started with Campaign APIs
description: Get started with Campaign APIs
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
---
# Get Started with [!DNL Campaign] APIs {#gs-ac-api}

[!DNL Adobe Campaign] comes with a set of Javascript functions which you can use:

* in Scripts - in [!DNL Adobe Campaign] workflows
* via APIs - from external systems

You can use JavaScript APIs to write in Campaign cloud database or read from the database:

* Business-specific APIs that let you act on each object: deliveries, workflows, subscriptions, and so on. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* Generic data access APIs for querying the data model data. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html){target="_blank"}.

Note that in its [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md),  Campaign works with two databases: a local database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud database for campaign execution, reporting, data ingestion, batch queries and workflow execution.

>[!CAUTION]
>
>* Starting Campaign v8.5.1, the authentication process to Campaign v8 changed. Technical operators must use Adobe Identity Management System (IMS) to connect to Campaign. Learn how to migrate your existing technical account(s) in [this technote](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 comes with a limit on the throughput (TPS) of our API layer. Breaking the limit leads to standard HTTP error (429). As a Managed Cloud Services user, you can contact Adobe to adapt the throttling for each API.
> 

## Prerequisites {#ac-api-prerequisites}

Before using [!DNL Adobe Campaign] APIs, you need to be familliar with the following topics:

* JavaScript
* SOAP protocol
* [!DNL Adobe Campaign] datamodel

In order to use APIs and interact with [!DNL Adobe Campaign], you also must be familiar with your data model.  

>[!NOTE]
>You can generate a complete description of your data model. Learn more in [this page](datamodel.md).


**Related topics**

* [Data model best practices](datamodel-best-practices.md)
