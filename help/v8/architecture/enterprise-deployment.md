---
title: Get started with Campaign FFDA deployment
description: Get started with Campaign FFDA deployment
feature: Architecture, FFDA
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
---
# [!DNL Campaign] FFDA deployment{#gs-ac-ffda}

By leveraging [[!DNL Snowflake]](https://www.snowflake.com/), a cloud database technology, Adobe Campaign Enterprise Full Federated Access (FFDA) deployment dramatically improves its scale and speed, with the ability to manage a more significant number of customer profiles, as well as much higher delivery rates and transactions per hour. 

## Benefits {#ffda-benefits}

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

## Campaign Enterprise (FFDA) architecture{#ffda-archi}

In an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 works with two databases: a local [!DNL Campaign] database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud [!DNL Snowflake] database for campaign execution, batch queries and workflow execution.

Campaign v8 Enterprise brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. 

Specific APIs are available to manage data between the local and the cloud database. Learn how these new APIs work and how to use them in [this page](new-apis.md).

General communication between servers and processes is carried out according to the following schema:

![](assets/architecture.png) 

* The execution and bounce management modules are disabled on the instance.
* The application is configured to perform message execution on a remote "mid-sourced" server that is driven using SOAP calls (over HTTP or HTTPS).

The [!DNL Snowflake] database on the marketing side is used to:

* Store all customer data: profiles, custom data such as transactions, products, locations, etc.
* Store all events and behavior data generated or collected by Campaign, such as delivery logs, tracking logs, push registrations, etc.
* Store all data aggregates of the above.
* Store a copy (h+1) of reference tables (such as deliveries, enumerations, countries, etc.) which are used in workflows, campaigns and reports.
* Run all batch processes and workloads


The PostgreSQL database on the marketing instance is used to:

* Execute certain workloads, such as low volume APIs.
* Store all Campaign data, including delivery and campaign settings, workflow and service definitions.
* Store all built-in reference tables (enumerations, countries, etc.) which are replicated to [!DNL Snowflake].
    
    However, you cannot:
    * create customizations for customer data, for example do not create a household table in PostgreSQL, but only in Snowflake
    * store any delivery logs, tracking logs, etc. on FFDA targeting dimension.
    * store large volume of data.


The PostgreSQL database on the mid-sourcing instance is used to:

* Execute batch and real-time (RT) deliveries.
* Send delivery and tracking logs - note that delivery and tracking log IDs are UUIDs and not 32-bit IDs.
* Collect and store tracking data.


## Impacts{#ffda-impacts}

### [!DNL Campaign] API staging mechanism{#staging-api}

With [!DNL Campaign] Cloud database, blast unitary calls are not recommended due to performance (latency & concurrency). Batch operation is always preferred. In order to guarantee optimal performances of APIs, Campaign keeps handling API calls at the local database level.

![](../assets/do-not-localize/glass.png) [API staging mechanism is detailed in this page](staging.md)

### New APIs{#new-apis}

New APIs are available to manage data synchronization between [!DNL Campaign] local database and Cloud database. A new mechanism has also been introduced to handle API calls at the local database level to avoid latency and increase the overall performance.

![](../assets/do-not-localize/glass.png) [New APIs are detailed in this page](new-apis.md)


### Data replication{#data-replication}

A specific technical workflow handles replication of tables that need to be present on both sides (Campaign  local database and Cloud database). This workflow is triggered every hour and relies on a new built-in JavaScript library.

>[!NOTE]
>
> Multiple replication policies have been created, based on the size of the table (XS, XL, etc.).
> Some tables are replicated in real-time, others will be replicated on an hourly basis. Some tables will have incremental updates, others will go through a full update.
>

[Learn more about Data replication](replication.md)

### ID management{#id-mgt-ffda}

Campaign v8 objects now use a **Universally Unique ID (UUID)**, which allows for unlimited unique values to identify data.

Please note that this ID is string-based and not sequential. The primary key is not a numerical value in Campaign v8, and you need to use **autouuid** and **autopk** attributes in your schemas.

In Campaign Classic v7 and earlier versions, the unicity of a key within a schema (i.e. table) is handled at the database engine's level. More generally, Classic Database engines like PostgreSQL, Oracle, or SQL Server include a native mechanism to prevent inserting duplicated rows based on a column or a set of columns via primary keys and/or unique indexes. Duplicated ID do not exist in these versions when proper index and primary keys are set at Database level.

Adobe Campaign v8 comes with Snowflake as the core Database. As it dramatically increases the scale of queries, the distributed architecture of the Snowflake database does not provide such mechanisms to manage then enforce the unicity of a key within a table. As a consequence, with Adobe Campaign v8, nothing prevents the ingestion of duplicated keys in a table. End-users are now responsible for ensuring consistency of Keys within the Adobe Campaign database. [Learn more](keys.md)

**Related topics**

* [Data model best practices](../dev/datamodel-best-practices.md)
