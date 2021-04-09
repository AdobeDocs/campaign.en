---
solution: Campaign Classic
product: campaign
title: What's new in Campaign v8
description: Learn more key capabilities
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493,bf4f3ed4-7c28-4852-895c-200766424f30
---
# What's new in Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 brings significant infrastructure, security, deliverability, and monitoring enhancements. By leveraging Snowflake, a cloud database technology, Adobe Campaign dramatically improves its scale and speed, with the ability to manage a more significant number of customer profiles, as well as much higher delivery rates and transactions per hour. 

Key capabilities include:

* **Speed and scale**. Adobe Campaign v8 leverages the Cloud Database Manager, leading to queries performing up to 200x faster, multi-petabyte scale, increased number of messages per hour, with up to 20M/hour or 1.5M/hour for transactional messages, and manage up to 200M active profiles with the potential to reach 1B.

* **Connections to the Adobe Experience Platform**. Adobe Campaign v8 supports data connectors with Adobe Experience Platform/RT-CDP, unified Customer Profile, and native integration with Journey Orchestration. These investments will optimize the Adobe Campaign customer experience and unlock new use cases such as the ability to add individualized real-time customer journeys to campaigns.

* **Managed Cloud Service**. Adobe Campaign v8 is available as a best-in-class Managed Cloud Service, providing proactive oversight, timely alerting, and service governance. The value for the marketer is more agile and scalable cross-channel campaign management.

## Scale

Campaign v8 brings end-to-end scale at any step of the process, from Targeting to the final reporting:

* Scale the volume of data you can handle (multi petabytes)
* Scale the performance of queries for segmentation and targeting but also data ingestion and egress
* Scale the delivery preparation (from hours to minutes)
And we simplify data management at the same time

## Simplification

* Simplify data management: index free, no database maintenance. With Campaign v8, no index is required on Cloud Database. You just need to create the tables, copy the data and you can start.

* Simplify accessibility through advanced sharing capabilities.


## Performances

Snowflake (aka Cloud Database) will bring you speed and endurance: no overload of the system activity peaks. 

The Cloud database technology does not require specific maintenance to guarantee the level of performance. In addition, you do not need to add indexes on schema to speed up the queries based on access patterns. 

As an existing Campaign Classic user, you should expect any big disruption in the way you usually "play" with Adobe Campaign. Most of changes are not visible, except small changes surfacing in the UI and configuration steps. 

Key changes: 

* Create segments up to 200x faster

* Increase speed of delivery

* Real-time reporting

## Campaign with Snowflake

Cloud storage is performed in Snowflake: a new external account ensures connectivity with the Cloud Database. [Learn more](#ac-gs-snowflake).

This is a foundational change in the software architecture. Data is now remote: Campaign federates the whole data, including Profiles. Campaign process now scales end to end, from Targeting to Delivery execution: Data ingestion, Segmentation, Targeting, queries, Delivery execution will now run in minutes.

This new version solves the whole challenge of Scaling, keeping the same level of flexibility & extensibility. The number of profiles isalmost unlimited, and data retention can be extended.

## Integrated ecosystem

You can integrate Campaign with a set of powerful Adobe solutions, such as: Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP, and more.

You can also configure predictive send time optimization and predictive engagement scoring with Journey AI, and increase open rates, clicks and revenues.

[Learn more about Campaign integrations](integration.md)

## Product configuration changes

### Campaign and Snowflake {#ac-gs-snowflake}

A new built-in external account is dedicated to Full FDA. This is the heart of Cloud Database connectivity. We recommend to leave as is. 

Any built-in schema/table which needs to be moved or replicated in Cloud Database come with a built-in schema extension under namespace **xxl**. As for schema extension the new XXL namespace will be used for any new piece of OOTB configuration like JavaScript, JSSP, etc.

Those extensions content any modification required to move built-in schemas from Campaign local database to Snowflake Cloud database and to adapt their structure accordingly: new UUID, updated links, etc.


>[!IMPORTANT]
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

[Learn more about Data replication](replication.md)


## ID management

Campaign v8 objects now use **Universally Unique ID (UUID)**, which implies unlimited unique values to identify data

Please not that this ID is string based and not sequential.
 

## Simplified maintenance

Campaign users do not need to be database experts: no more database maintenance long workflows or complex table indexing.
