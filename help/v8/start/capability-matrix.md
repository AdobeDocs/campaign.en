---
title: Campaign Classic v7 - Campaign v8 capability matrix
description: Understand differences between Campaign Classic v7 and Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
---
# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 capabilities{#gs-matrix}

As a former [!DNL Campaign Classic] v7 user, you should not expect any big disruption in the way you usually interact with [!DNL Adobe Campaign]. Most changes in v8 are not visible, except for small changes surfacing in the UI and configuration steps. 

Adobe Campaign v8 is available as a **Managed Cloud Service**. The new offering combines best-in-class services with proactive oversight and timely alerting, focusing on three areas:

* **Cloud agility** — automation by Adobe, featuring optimized, standardized cloud deployments for more predictable performance, greater agility, and improved self-service productivity.
* **Service experience** — proactive availability, capacity, and performance monitoring and response to prevent disruptions, resolve incidents faster, and review service regularly for continuous improvement.
* **Deep Campaign expertise** — high-affinity service from expert Customer Engineering teams to meet functional, technical, or deliverability needs, cut deployment risk, and improve change management.

As a former [!DNL Campaign Classic] user, note that most of the [!DNL Campaign Classic] v7 features are available with [!DNL Campaign] v8, except a small set of them, listed in [this section](#gs-removed). Others will come in future releases. [Learn more in this section](#gs-unavailable-features)

![](../assets/do-not-localize/glass.png) Learn more about [!DNL Campaign] v8 architecture in [this page](../architecture/architecture.md).

## [!DNL Campaign] and [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 works with [!DNL Snowflake]. Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

    In its **[!DNL Snowflake] FDA (default) deployment**, [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

    In its **[Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md)**, [!DNL Adobe Campaign] v8 works with two databases: a local [!DNL Campaign] database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud [!DNL Snowflake] database for campaign execution, batch queries and workflow execution.

    Campaign v8 Enterprise brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. With this new architecture, Campaign v8 Enterprise (FFDA) deployment simplifies data management: no index is required on the Cloud Database. You just need to create the tables, copy the data and you can start. The Cloud database technology does not require specific maintenance to guarantee the level of performance.

    As a Campaign Enterprise (FFDA) offering user, expect changes in data management, configuration and product architecture. Learn more in [this section](../architecture/enterprise-deployment.md).

Learn more about Campaign v8 architecture in [this section](../architecture/architecture.md).

## Use your Adobe ID to connect to Campaign{#adobe-id}

Campaign users connect through their Adobe ID. The same Adobe ID is used to keep all your Adobe plans and products associated with a single account, for all Adobe Experience Cloud solutions. 

![](../assets/do-not-localize/glass.png) Learn how to connect to [!DNL Campaign] in [this page](connect.md).

## Analyze data with cubes{#adobe-reporting}

Use the Marketing Analytics module to analyze and measure data, calculate statistics, simplify and optimize report creation and calculation. In addition, create reports and build target populations: once identified, they are stored in lists that can be used in Adobe Campaign (targeting, segmentation, etc.).

Adobe Campaign cube reports are optimized and bring better scale capabilities than Campaign Classic v7. Former limitations on Cubes do not apply in Campaign v8.

## Change data source {#change-data-source}

Campaign v8 offers an additional targeting workflow activity: **[!UICONTROL Change data source]**.

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]** to manage data across different data sources such as FDA, FFDA and local database.

![](../assets/do-not-localize/glass.png) Learn more on the **[!UICONTROL Change data source]** activity in [this page](../config/workflows.md#change-data-source-activity).

## Unavailable features{#gs-unavailable-features}

Please note that some capabilities are not available in this version of Campaign, such as:

* Marketing Resource Management
* Distributed Marketing
* Response Manager
* Hybrid/On-premise deployment models

>[!CAUTION]
>
>* For now, Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 
>
>* Migration from an existing Campaign Classic v7 environment is not yet available.
>
>* If you are unsure of your deployment model or have any question, please get in touch with your Adobe Account executive.

## Unsupported features{#gs-removed}

To align with Campaign v8 new architecture and deployment model, some historic Campaign Classic v7 capabilities are no longer supported with Campaign v8, such as:

* Coupons
* Web tracking
* Surveys
* Social Marketing with Facebook
* ACS Connector (Prime offering)
* Integration with LDAP
* User/Password sign in

>[!NOTE]
>
>Some non-available or unsupported features may still be visible in the user interface.
