---
product: campaign
title: Edit schema
description: Learn more about the Edit schema workflow activity
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# Edit schema{#edit-schema}



Data can be transformed, normalized and, if necessary, enriched in the workflow using the **[!UICONTROL Edit schema]** activity. It is generally used to normalize the data structure: you can rename the output columns or modify their content, by calculating the average values of a field or aggregate for example.

This activity does not change the data in the work table, it changes only its schema, i.e. the logical view of the data.

![](assets/wf_manipulation_box.png)

You can also create joins with other worktables, via the **[!UICONTROL Links]** tab.

![](assets/wf_manipulation_box_link_tab.png)

The lower section lets you configure the list of joining conditions, i.e. the criteria used for reconciling the data from the two tables.
