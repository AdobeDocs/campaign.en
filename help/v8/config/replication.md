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
    This workflow performs automatic replication of reference tables that need to be present on Campaign local database (Postgres) and Cloud database ([!DNL Snowflake]). It is scheduled to execute every hour, daily. If **lastModified** field exists, replication happens incrementally, otherwise the whole table is replicated. The order of the tables in the array below is the order used by the replication workflow.
* **[!UICONTROL Replicate Staging data]**
    This workflow replicates staging data for unitary calls. It is scheduled to execute every hour, daily.
* **[!UICONTROL Deploy FFDA immediately]**  
    This workflow performs an immediate deployment to the Cloud database.
* **[!UICONTROL Replicate FFDA data immediately]**
    This workflow replicates the XS data for a given external account.

These technical workflows are available from the **[!UICONTROL Administration > Production > Technical workflows > Full FFDA replication]** node of Campaign Explorer.

**SHOULD WE ADD THIS? https://wiki.corp.adobe.com/display/neolane/Full+FDA+%3A%3A+Replication+strategy**


**Related topics**

:arrow_upper_right: Learn how to get started with worflows in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

:bulb: Access data retention periods in [this section](../dev/datamodel-best-practices.md#data-retention)


## Data replication{#data-replication}

Tables are replicated from Campaign database to [!DNL Snowflake] Cloud database through dedicated workflows decribed above.

Replication policies are based on the size of the table. Some tables will be replicated. Some tables will be replicated in real-time, come others will be replicated on hourly basis. Some tables will have incremental updates when others will be replaced.

| Namespace | Table | workflow replication | Real-time replication |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK**| xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:report<br>xtk:olapCube<br>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br>| Yes (incremental)| Yes |
| **XTK**| xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights| Yes (full)| Yes|
| **NMS**| nms:budget<br>nms:program<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:delivery (immediate replication)<br>nms:seedMember<br>nms:webApp<br>nms:trackingUrl (immediate replication)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offer<br>nms:offerView<br>nms:recipient (incremental?)<br>nms:group<br>nms:dlvExclusion<br>nms:stock | Yes (incremental)    | Yes |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:category<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp<br>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:expenseLine<br>nms:costLine | Yes (full) | Yes|
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:broadLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:propositionRcp<br>nms:localValidationRcp<br>nms:visitor<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webAppLogRcp<br>nms:appSubscriptionRcp<br>nms:broadLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms:eventHisto<br>nms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:subscription<br>nms:subHisto<br>nms:trackingStats (Snowflake usage only)<br>nms:tmpBroadcast (Snowflake usage only)<br>nms:tmpBroadcastExclusion (Snowflake usage only)<br>nms:tmpBroadcastPaper (Snowflake usage only) | No                   | No |

