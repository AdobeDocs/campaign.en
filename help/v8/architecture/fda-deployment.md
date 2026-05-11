---
title: Get started with Campaign FDA deployment
description: Get started with Campaign FDA deployment
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: ee3dfd63-9a21-4961-9f24-ea3385284a21
    internal-label: Federated Data Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# [!DNL Campaign] FDA deployment{#gs-fda}

In its Campaign FDA (default) deployment, [!DNL Adobe Campaign] v8 can be connected to [!DNL Snowflake] to access data through [Federated Data Access](../connect/fda.md) capability: you can then access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. 

>[!NOTE]
>
>In this deployment model, the [!DNL Snowflake] secondary database is available upon request only. To have your deployment updated with [!DNL Snowflake], contact your Adobe Transition Manager.
>

## Benefits{#fda-benefits}

This deployment model comes with the following benefits:

* **Storage and performances**
    You can move your historical data to [!DNL Snowflake] and then reduce dependencies to Adobe Campaign IDs limit. This architecture also reduce your dependency to PostgreSQL storage and performances limits. As less data is stored in Campaign database, performances are better and maintenance tasks are performed faster.

* **Data model extension and data management**
    You can create tables in [!DNL Snowflake] and link them to Adobe Campaign, for example to use archived data over retention periods, or run segmentation processes with outstanding performances.

    This architecture also allows you to use data management workflow capabilities in [!DNL Snowflake]. Only aggregates and temporary tables are moved to Campaign for personalization and delivery purpose.


## Architecture{#fda-archi}

With this deployment model, Adobe Campaign users can extend their data into [!DNL Snowflake] and leverage the benefits of a single, integrated data platform for powerful marketing campaign data insights in real-time. It provides users with the ability to unlock deep value from their data by offering a single, unified, and easy-to-use platform for data analysis. The cloud data platform requires no management as it infinitely scales to support any volume of marketing data from Adobe Campaign.

General communication between servers and processes is carried out according to the following schema:

![](assets/fda-architecture.png) 

PostgreSQL is the primary database, and Snowflake can be used as the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.
