---
product: campaign
title: Update aggregate
description: Learn more about the Update aggregate workflow activity
feature: Workflows
exl-id: d2b26af0-30a1-4852-acd5-996795f198a1
---
# Update aggregate{#update-aggregate}

Aggregates are defined at cube level for reporting purposes. A **[!UICONTROL Workflow]** tab is available when configuring an aggregate.

For more information on cubes and using aggregates in Adobe Campaign, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html){target="_blank"}.


To update an aggregate, edit the **[!UICONTROL Update aggregate]** activity and select the Cube and aggregate to update. 

You can perform a **Full update** or a**Partial update**.

By default, a full update is executed out during each calculation. To enable a partial update, select the relevant option and define the update conditions.

**Good practice**: a **[!UICONTROL Scheduler]** activity can be used to specify the frequency of calculation updates.

![](assets/scheduler-and-cube-aggregate.png)
