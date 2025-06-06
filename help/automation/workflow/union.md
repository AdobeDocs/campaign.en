---
product: campaign
title: Union
description: Learn more about the Union workflow activity
feature: Workflows, Targeting Activity
version: Campaign v8, Campaign Classic v7
exl-id: 4109e198-bf9d-4dd2-92a1-16bbadbe30e8
---
# Union{#union}

A **[!UICONTROL Union]** groups the result of several inbound activities in a single target. The target is created with all results received: all prior activities must therefore be finished for the union to be executed. 

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>For more on configuring and using the **[!UICONTROL Union]** activity, refer to [this page](targeting-workflows.md#combining-several-targets--union-).

## Union example {#union-example}

In the following example, the results from two queries have been combined in order to update the list. The two queries target the recipients. The results are therefore based on the same table.

1. Insert a **[!UICONTROL Union]** -type activity straight after the two queries and before an update-type activity of the list then open it.
1. You may enter a label.
1. Select the **[!UICONTROL Keys only]** reconciliation method since, in this example, the population resulting from queries contains consistent data.
1. If you have added additional data for the queries, you can decide to keep only the data that is shared.
1. If you wish to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** option.

   Specify this final number by entering the maximum number of recipients and by selecting the query whose population will take priority.

1. Approve the **[!UICONTROL Union]** activity then configure the [List update](list-update.md) activity.
1. Start the workflow. The number of results is displayed and the list defined in the list update activity is created or updated. This list contains the set of recipients for both queries or, where applicable, the number defined at the previous step.

   ![](assets/union_example.png)

## Input parameters {#input-parameters}

* tableName
* schema

Each inbound event must specify a target defined by these parameters.

## Output parameters {#output-parameters}

* tableName
* schema
* recCount

This set of three values identifies the target resulting from the union. **[!UICONTROL tableName]** is the name of the table that records the target identifiers, **[!UICONTROL schema]** is the schema of the population (usually nms:recipient) and **[!UICONTROL recCount]** is the number of elements in the table.
