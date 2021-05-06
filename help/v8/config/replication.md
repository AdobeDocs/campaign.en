---
solution: Campaign Classic
product: campaign
title: Technical workflows and data replication
description: Technical workflows and data replication
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
---
# Technical workflows and data replication

## Technical workflows

Adobe Campaign comes with a set of built-in technical workflows. Technical workflows execute processes or jobs, scheduled on a regular basis on the server.

These workflows perform maintenance operations on the database, leverage the tracking information in the delivery logs, create recurring campaigns, and more.

:arrow_upper_right: The full list of technical workflows is detailed in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

In addition to these technical workflows, Campaign v8 relies on specific technical workflows to manage [data replication](#data-replication).

* **[!UICONTROL Replicate Reference tables]**
    This workflow performs automatic replication of reference tables that need to be present on Campaign local database (Postgres) and Cloud database (Snowflake). It is scheduled to execute every hour, daily. If **lastModified** field exists, replication happens incrementally, otherwise the whole table is replicated. The order of the tables in the array below is the order used by the replication workflow.
* **[!UICONTROL Replicate Staging data]**
    This workflow replicates staging data for unitary calls. It is scheduled to execute every hour, daily.
* **[!UICONTROL Deploy FFDA immediately]**  
    This workflow performs an immediate deployment to the Cloud database.
* **[!UICONTROL Replicate FFDA data immediately]**
    This workflow replicates the XS data for a given external account.

These technical workflows are available from the **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** node of Campaign Explorer.

## Data replication{#data-replication}

Tables are replicated from Campaign database to Snowflake Cloud database through dedicated workflows decribed above.

Replication policies are based on the size of the table. Some tables will be replicated. Some tables will be replicated in real-time, come others will be replicated on hourly basis. Some talbes will have incremental updates when others will be replaced.

**SHOULD WE LIST ALL TABLES?**

TO CHECK

**Related topics**

:arrow_upper_right: Learn how to get started with worflows in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Access data retention periods in [this section](../dev/datamodel-best-practices.md#data-retention)
