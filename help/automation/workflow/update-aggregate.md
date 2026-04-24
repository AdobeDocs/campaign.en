---
product: campaign
title: Update aggregate
description: Learn more about the Update aggregate workflow activity
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Update aggregate{#update-aggregate}

Aggregates defined in [cubes](../../v8/reporting/gs-cubes.md) for reporting purposes can be updated with a specific activity. A **[!UICONTROL Workflow]** tab is available when configuring the aggregate.

Learn more about cubes and aggregates in [this section](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

To update an aggregate, edit the **[!UICONTROL Update aggregate]** activity and select the cube and aggregate to update.

You can configure a **Full update** or a **Partial update**.

![](assets/update-aggregate-details.png)

By default, a full update is executed out during each calculation. To enable a partial update, select the option and define the update conditions.

![](assets/update-aggregate-partial.png)

A good practice is to add a **[!UICONTROL Scheduler]** activity to set up the frequency of calculation updates.
