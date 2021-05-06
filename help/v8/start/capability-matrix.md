---
solution: Campaign Classic
product: campaign
title: Campaign Classic v7 - Campaign v8 capability matrix
description: Understand differences between Campaign Classic v7 and Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
---
# Campaign Classic v7 - Campaign v8 capabilities{#gs-matrix}


As an existing Campaign Classic v7 user, you should expect any big disruption in the way you usually "play" with Adobe Campaign. Most of changes are not visible, except small changes surfacing in the UI and configuration steps. 

Key changes: 

* Create segments up to 200x faster

* Increase speed of delivery

* Real-time reporting

As a Campaign Classic user, note that most of the Campaign Classic v7 features are available with Campaign v8, except a small set of them, listed in [this section](#gs-removed). Others will come in future releases. [Learn more](#gs-unavailable-features)


## Product configuration changes

### Campaign and [!DNL Snowflake] {#ac-gs-snowflake}

Cloud storage is performed in [!DNL Snowflake]: a new external account ensures connectivity with the Cloud Database. [Learn more](#ac-gs-snowflake).

This is a foundational change in the software architecture. Data is now remote: Campaign federates the whole data, including Profiles. Campaign process now scales end to end, from Targeting to Delivery execution: Data ingestion, Segmentation, Targeting, queries, Delivery execution will now run in minutes.

This new version solves the whole challenge of Scaling, keeping the same level of flexibility & extensibility. The number of profiles is almost unlimited, and data retention can be extended.

A new built-in **external account** is dedicated to Full FDA. This is the heart of Cloud Database connectivity. We recommend to leave as is.  

Any built-in schema/table which needs to be moved or replicated in Cloud Database come with a built-in schema extension under namespace **xxl**. As for schema extension the new XXL namespace will be used for any new piece of OOTB configuration like JavaScript, JSSP, etc.

Those extensions content any modification required to move built-in schemas from Campaign local database to [!DNL Snowflake] Cloud database and to adapt their structure accordingly: new UUID, updated links, etc.

>[!CAUTION]
>
> Customer data is not stored in the local Campaign database. As a consequence, any custom table needs to be create in the Cloud database.
>

### Data replication

A specific technical workflow handles replication of tables that need to be present on both sides (Campaign  local database and Cloud database). This workflow is triggered every hour and relies on a new built-in JavaScript library.

>[!NOTE]
>
> Multiple replication policies have been created, based on the size of the table (XS, XL, etc.).
> Some tables are replicated in real-time as others will be on hourly basis. Some tables will have incremental updates as others will be full update.
>

[Learn more about Data replication](../config/replication.md)

### ID management

Campaign v8 objects now use **Universally Unique ID (UUID)**, which implies unlimited unique values to identify data

Please not that this ID is string based and not sequential.
 
### Simplified maintenance

Campaign users do not need to be database experts: no more database maintenance long workflows or complex table indexing.

## Temporary unavailable features{#gs-unavailable-features}

Please note that some capabilities are not available in this first version but will be released soon, such as:

* Marketing Resource Management
* Distributed Marketing
* Offer Management inbound messages (Interaction module)
* Campaign Optimization
* Response Manager
* Social marketing with Twitter
* Hybrid/On-premise deployment models

## Removed features{#gs-removed}

To align with Campaign v8 new architecture and deployment model, some historic Campaign Classic v7 capabilities are not available in Campaign v8.

* Coupons
* Web tracking
* Surveys
* Social Marketing with Facebook
* ACS Connector (Prime offering)
* Microsoft SQL database
* Oracle database
