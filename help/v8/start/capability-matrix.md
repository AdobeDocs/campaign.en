---
product: Adobe Campaign
title: Campaign Classic v7 - Campaign v8 capability matrix
description: Understand differences between Campaign Classic v7 and Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
---
# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8 capabilities{#gs-matrix}

As an existing [!DNL Campaign Classic] v7 user, you should not expect any big disruption in the way you usually interact with [!DNL Adobe Campaign]. Most changes in v8 are not visible, except for small changes surfacing in the UI and configuration steps. 

Key changes: 

* Create segments up to 200x faster
* Increase speed of delivery
* Real-time reporting with Cubes

As a [!DNL Campaign Classic] user, note that most of the [!DNL Campaign Classic] v7 features are available with [!DNL Campaign] v8, except a small set of them, listed in [this section](#gs-removed). Others will come in future releases. [Learn more in this section](#gs-unavailable-features)

💡 Learn more about [!DNL Campaign] v8 architecture in [this page](../dev/architecture.md).

## Product configuration changes

### [!DNL Campaign] and [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 works with two databases: a local database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud database for campaign execution, batch queries and workflow execution.

This is a foundational change in the software architecture. Data is now remote and Campaign federates the whole data, including Profiles. [!DNL Campaign] processes now scales end-to-end, from targeting to message execution: data ingestion, segmentation, targeting, queries, deliveries will now typically run in minutes. This new version solves the whole challenge of scaling while keeping the same level of flexibility & extensibility. The number of profiles is almost unlimited, and data retention can be extended.

Cloud storage is performed in **[!DNL Snowflake]**: a new built-in **external account** ensures connectivity with the Cloud Database. It is configured by Adobe and must not be modified. [Learn more](../config/external-accounts.md)

Any built-in schema/table which needs to be moved or replicated in Cloud Database comes with a built-in schema extension under the **xxl** namespace. Those extensions contain any modification required to move built-in schemas from the [!DNL Campaign] local database to the [!DNL Snowflake] Cloud database and to adapt their structure accordingly: new UUID, updated links, etc.

>[!CAUTION]
>
> Customer data is not stored in the local [!DNL Campaign] database. As a consequence, any custom table needs to be create in the Cloud database.
>

Specific APIs are available to manage data between the local and the cloud database. Learn how these new APIs work and how to use them in [this page](../dev/new-apis.md).

### Data replication

A specific technical workflow handles replication of tables that need to be present on both sides (Campaign  local database and Cloud database). This workflow is triggered every hour and relies on a new built-in JavaScript library.

>[!NOTE]
>
> Multiple replication policies have been created, based on the size of the table (XS, XL, etc.).
> Some tables are replicated in real-time, others will be replicated on an hourly basis. Some tables will have incremental updates, others will go through a full update.
>

[Learn more about Data replication](../config/replication.md)

### ID management

Campaign v8 objects now use a **Universally Unique ID (UUID)**, which allows for unlimited unique values to identify data.

Please note that this ID is string-based and not sequential. The primary key is not a numerical value in Campaign v8, and you need to use **autouuid** and **autopk** attributes in your schemas.

In Campaign Classic v7 and earlier versions, the unicity of a key within a schema (i.e. table) is handled at the database engine's level. More generally, Classic Database engines like PostgreSQL, Oracle, or SQL Server include a native mechanism to prevent inserting duplicated rows based on a column or a set of columns via primary keys and/or unique indexes. Duplicated ID do not exist in these versions when proper index and primary keys are set at Database level.

Adobe campaign v8 comes with Snowflake as the core Database. As it dramatically increases the scale of queries, the distributed architecture of the Snowflake database does not provide such mechanisms to manage then enforce the unicity of a key within a table. As a consequence, with Adobe Campaign v8, nothing prevents the ingestion of duplicated keys in a table. End-users are now responsible for ensuring consistency of Keys within the Adobe Campaign database. [Learn more](../dev/keys.md)

### Simplified maintenance

Campaign users do not need to be database experts: there is no longer any need for complex database maintenance operations or complex table indexing.

## Connection to Campaign

Campaign users connect through their Adobe ID. The same Adobe ID is used to keep all your Adobe plans and products associated with a single account. 

💡 Learn how to connect to [!DNL Campaign] in [this page](connect.md).

## Reporting

 Note that Adobe Campaign reports are optimized and offer better scale capabilities than Campaign Classic v7. Existing limitations on Cubes do not apply.

## Unavailable features{#gs-unavailable-features}

Please note that some capabilities are not available in this first version, such as:

* Marketing Resource Management
* Distributed Marketing
* Inbound Offer Management (Interaction module)
* Campaign Optimization
* Response Manager
* Hybrid/On-premise deployment models
* LINE messaging
* Campaign Control Panel

>[!CAUTION]
>
>For now, Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 
>
>Migration from an existing Campaign Classic v7 environment is not yet available.
>
>If you are unsure of your deployment model or have any question, please get in touch with your account team.

## Removed features{#gs-removed}

To align with Campaign v8 new architecture and deployment model, some historic Campaign Classic v7 capabilities are no longer available in Campaign v8.

* Coupons
* Web tracking
* Surveys
* Social Marketing
* ACS Connector (Prime offering)
* Integration with LDAP
* User/Password sign in
