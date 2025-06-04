---
title: Change data source
description: Learn more about the Change data source activity
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
---
# Change data source {#change-data-source}

Use the **[!UICONTROL Change data source]** activity to change the data source of a [workflow working table](use-workflow-data.md#workflow-temporary-work-table). This activity provides more flexibility to manage data across different data sources such as Federated Data Access (FDA), Campaign Cloud database (FFDA) and Campaign Local database.

The workflow **[!UICONTROL Working table]** is used to handle and share data with the workflow activities. 

By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data you need to query on.
For example, when querying the **[!UICONTROL Recipients]** table, stored on the Cloud database, the workflow creates a **[!UICONTROL Working table]** on the same Cloud database.

Use a **[!UICONTROL Change Data Source]** activity to use a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you need to switch back to the Cloud database to continue the workflow execution.

>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.

To use the **[!UICONTROL Change Data Source]** activity, you must:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to this [page](query.md#create-a-query).

1. Add a **[!UICONTROL Change data source]** activity.

   ![](assets/change-data-source.png)

1. Edit your **[!UICONTROL Change data source]** activity to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default Campaign Local database.

   ![](assets/change-data-source_2.png)

1. Add a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to the [this page](sql-code-and-javascript-code.md#javascript-code).

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
1. Edit this activity and select **[!UICONTROL Active FDA external account]**, and the corresponding **[!UICONTROL External database]** external account.

   ![](assets/change-data-source_3.png)

1. You can now start your workflow.
