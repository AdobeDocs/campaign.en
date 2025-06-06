---
product: campaign
title: Edit schema
description: Learn more about the Edit schema workflow activity
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
---
# Edit schema{#edit-schema}



Data can be transformed, normalized and, if necessary, enriched in the workflow using the **[!UICONTROL Edit schema]** activity. It is generally used to normalize the data structure: you can rename the output columns or modify their content, by calculating the average values of a field or aggregate for example.

This activity does not change the data in the work table, it changes only its schema, i.e. the logical view of the data.

![](assets/wf_manipulation_box.png)

You can also create joins with other worktables, via the **[!UICONTROL Links]** tab.

![](assets/wf_manipulation_box_link_tab.png)

The lower section lets you configure the list of joining conditions, i.e. the criteria used for reconciling the data from the two tables.
