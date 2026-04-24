---
title: Get started with Campaign APIs
description: Get started with Campaign APIs
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
TQID: https://experienceleague.adobe.com/pC27h6Z-J345l4XjFEOgwVTHtQSSRxJmtnWQ973SiPk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Get Started with [!DNL Campaign] APIs {#gs-ac-api}

[!DNL Adobe Campaign] comes with a set of Javascript functions which you can use:

* in Scripts - in [!DNL Adobe Campaign] workflows
* via APIs - from external systems

>[!NOTE]
>
>Depending on your deployment model, you can also use REST APIs with Campaign v8. [Learn more](../dev/api/get-started-apis.md).

You can use [Campaign JavaScript APIs](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"} to write in Campaign cloud database or read from the database:

* Business-specific APIs that let you act on each object: deliveries, workflows, subscriptions, and so on. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html){target="_blank"}.
* Generic data access APIs for querying the data model data using `queryDef` and the `NLWS` object. Learn more in [Query the database with queryDef](query-api.md).

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
* [!DNL Adobe Campaign] data model

In order to use APIs and interact with [!DNL Adobe Campaign], you also must be familiar with your data model.  

>[!NOTE]
>You can generate a complete description of your data model. Learn more in [this page](datamodel.md).


**Related topics**

<!-- * [Query the database with queryDef](query-api.md)-->
* [Data model best practices](datamodel-best-practices.md)
* [Campaign JSAPI documentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
