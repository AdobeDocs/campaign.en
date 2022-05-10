---
title: Get started with Campaign FFDA deployment
description: Get started with Campaign FFDA deployment
feature: Overview
role: Data Engineer
level: Beginner
---
# [!DNL Campaign] FFDA deployment{#gs-ac-ffda}

By leveraging [[!DNL Snowflake]](https://www.snowflake.com/), a cloud database technology, Adobe Campaign Enterprise Full Federated Access (FFDA) deployment dramatically improves its scale and speed, with the ability to manage a more significant number of customer profiles, as well as much higher delivery rates and transactions per hour. 

Campaign v8 Enterprise (FFDA) brings end-to-end scale at any step of the process, from targeting to the final reporting:

* Scale the volume of data you can handle (until 8 TB)
* Scale the performance of queries for segmentation and targeting but also data ingestion and egress
* Scale the delivery preparation (from hours to minutes)

This is a foundational change in the software architecture. Data is now remote and Campaign federates the whole data, including Profiles. [!DNL Campaign] processes now scales end-to-end, from targeting to message execution: data ingestion, segmentation, targeting, queries, deliveries will now typically run in minutes. This new version solves the whole challenge of scaling while keeping the same level of flexibility & extensibility. The number of profiles is almost unlimited, and data retention can be extended.

Cloud storage is performed in **[!DNL Snowflake]**: a new built-in **external account** ensures connectivity with the Cloud Database. It is configured by Adobe and must not be modified. [Learn more](../config/external-accounts.md)

Any built-in schema/table which needs to be moved or replicated in Cloud Database comes with a built-in schema extension under the **xxl** namespace. Those extensions contain any modification required to move built-in schemas from the [!DNL Campaign] local database to the [!DNL Snowflake] Cloud database and to adapt their structure accordingly: new UUID, updated links, etc.

>[!CAUTION]
>
> Customer data is not stored in the local [!DNL Campaign] database. As a consequence, any custom table needs to be create in the Cloud database.
>

Specific APIs are available to manage data between the local and the cloud database. Learn how these new APIs work and how to use them in [this page](new-apis.md).

## [!DNL Campaign] API staging mechanism

With [!DNL Campaign] Cloud database, blast unitary calls are not recommended due to performance (latency & concurrency). Batch operation is always preferred. In order to guarantee optimal performances of APIs, Campaign keeps handling API calls at the local database level.

![](../assets/do-not-localize/glass.png) [API staging mechanism is detailed in this page](staging.md)

## New APIs

New APIs are available to manage data synchronization between [!DNL Campaign] local database and Cloud database. A new mechanism has also been introduced to handle API calls at the local database level to avoid latency and increase the overall performance.

![](../assets/do-not-localize/glass.png) [New APIs are detailed in this page](new-apis.md)


## Data replication

A specific technical workflow handles replication of tables that need to be present on both sides (Campaign  local database and Cloud database). This workflow is triggered every hour and relies on a new built-in JavaScript library.

>[!NOTE]
>
> Multiple replication policies have been created, based on the size of the table (XS, XL, etc.).
> Some tables are replicated in real-time, others will be replicated on an hourly basis. Some tables will have incremental updates, others will go through a full update.
>

[Learn more about Data replication](replication.md)

## ID management

Campaign v8 objects now use a **Universally Unique ID (UUID)**, which allows for unlimited unique values to identify data.

Please note that this ID is string-based and not sequential. The primary key is not a numerical value in Campaign v8, and you need to use **autouuid** and **autopk** attributes in your schemas.

In Campaign Classic v7 and earlier versions, the unicity of a key within a schema (i.e. table) is handled at the database engine's level. More generally, Classic Database engines like PostgreSQL, Oracle, or SQL Server include a native mechanism to prevent inserting duplicated rows based on a column or a set of columns via primary keys and/or unique indexes. Duplicated ID do not exist in these versions when proper index and primary keys are set at Database level.

Adobe Campaign v8 comes with Snowflake as the core Database. As it dramatically increases the scale of queries, the distributed architecture of the Snowflake database does not provide such mechanisms to manage then enforce the unicity of a key within a table. As a consequence, with Adobe Campaign v8, nothing prevents the ingestion of duplicated keys in a table. End-users are now responsible for ensuring consistency of Keys within the Adobe Campaign database. [Learn more](keys.md)

**Related topics**

* [Data model best practices](../dev/datamodel-best-practices.md)
