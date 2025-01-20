---
title: Technical workflows and data replication
description: Technical workflows and data replication
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
---

# Data replication {#wf-data-replication}
 
## Principle

In the context of an [Enterprise (FFDA) deployment](enterprise-deployment.md), data replication ensures that the two databases, PostgreSQL and Snowflake, are operational in parallel and remain synchronized in real-time.

The Snowflake Database is optimized for handling large data batches, such as updating 1 million addresses. Meanwhile, the local PostgreSQL Database is better suited for individual or small-volume operations, like updating a single seed address. Synchronization occurs automatically and transparently in the background, ensuring data in PostgreSQL is duplicated in Snowflake in real time, keeping both databases identical. Data synchronization involves schemas and tables, and data.

➡️ [Discover how data replication works in video](#video) 

## Replication modes {#modes}

Data replication can occur in different modes depending on the use case. 

* **On-the-fly replication** handles cases where real-time duplication is essential. It relies on specific technical threads to replicate data immediately for use cases like creating a diffusion or updating a seed address.
* **Scheduled replication** is used when immediate synchronization is not required. Scheduled replication uses specific [technical workflows](#workflows) that run every hour to synchronize data, such as typology rules. 

## Replication Policies

Replication policies define how much data is replicated from a PostgreSQL table. These policies depend on the size of the table and the specific use case. Some tables will have incremental updates when others will be replicated. There are three main types of replication policies:

* **XS**: This policy is used for tables with relatively small sizes. The entire table is replicated in one shot. Incremental replication avoids repeatedly replicating the same data by using a timestamp pointer to replicate only recent changes.
* **SingleRow**: This policy replicates only one row at a time. It is typically used for on-the-fly replication involving current Campaign objects and related objects.
* **SomeRows**: This policy is designed for replicating a limited subset of data using query definitions or filters. It is used for larger tables where selective replication is necessary.

## Replication Workflows {#workflows}

Campaign v8 relies on specific technical workflows to manage scheduled data replication. These technical workflows are available from the **[!UICONTROL Administration > Production > Technical workflows > Full FFDA Replication]** node of Campaign Explorer. **They must not be modified.**

Technical workflows execute processes or jobs, scheduled on a regular basis on the server. These workflows perform maintenance operations on the database, leverage the tracking information in the delivery logs, create recurring campaigns, and more. The full list of technical workflows is detailed in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}.

Technical workflows ensuring data replication are:

* **[!UICONTROL Replicate Reference tables]**: Performs automatic replication of built-in tables that need to be present on Campaign local database (Postgres) and Cloud database ([!DNL Snowflake]). It is scheduled to execute every hour, daily. If **lastModified** field exists, replication happens incrementally, otherwise the whole table is replicated. The order of the tables in the array below is the order used by the replication workflow.
* **[!UICONTROL Replicate Staging data]**: Replicates staging data for unitary calls. It is scheduled to execute every hour, daily.
* **[!UICONTROL Deploy FFDA immediately]** : Performs an immediate deployment to the Cloud database.
* **[!UICONTROL Replicate FFDA data immediately]**: Replicates the XS data for a given external account.

If needed, you can launch data synchronization manually. To do this, right-click on the **Scheduler** activity and select **Execute pending task(s) now**.

In addition to the built-in **Replicate Reference Tables** technical workflow, you can force data replication in your workflows using one of these methods

+++How to force data replication

* Add a specific **Javascript code** activity with the following code:

    ```
    nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
    ```

    ![](assets/jscode.png)

* Add a specific **nlmodule** activity with the following command:

    ```
    nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
    ```

    ![](assets/nlmodule.png)

+++

>[!NOTE]
>
>On-the-fly replication is handled by specific technical threads rather than workflows. Configuration for this mode is managed in the serverConf.xml file. You can configure the serverConf.xml to match specific use cases, such as requesting that XS tables are incrementally replicated rather than entirely. For more information, contact your Adobe representative.

## APIs

APIs enable replication of both custom and out-of-the-box data from PostgreSQL to Snowflake. These APIs allow you to bypass predefined workflows and customize replication for specific requirements, such as replicating custom tables.

Example:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="hm:recipientLookupFolder"/>
    </params>
);
```

## Replication queues

When high volumes of replication requests occur simultaneously, performance issues may arise in Snowflake due to table-level locks during MERGE operations. To mitigate this, centralized replication workflows group requests into queues.

Each queue is handled by a technical workflow, which manages replication for a specific table, executing pending requests as a single MERGE operation. These workflows are triggered every 20 seconds to process new replication requests:

* **Replicate nmsDelivery**: Queue for the nms:delivery table.
* **Replicate nmsDlvExclusion**: Queue for the nms:dlvExclusion table.
* **Replicate nmsDlvMidRemoteIdRel**: Queue for the nms:dlvRemoteIdRel table.
* **Replicate nmsTrackingUrl**, **Replicate nmsTrackingUrl**: Queues in concurrency for the nms:trackingUrl table, utilizing two workflows to improve efficiency by processing requests based on different priorities.

## Tutorial {#video}

This video presents the key concepts of which databases Adobe Campaign v8 uses, why data is being replicated, which data is being replicated and how the replication process works.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

Additional Campaign v8 Client Console tutorials are available [here](https://experienceleague.adobe.com/en/docs/campaign-learn/tutorials/overview)).
