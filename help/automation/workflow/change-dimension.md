---
product: campaign
title: Change dimension in a workflow
description: Learn how to use the Change dimension activity
feature: Workflows, Targeting Activity
role: User
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
---
# Change dimension{#change-dimension}

Use the **[!UICONTROL Change dimension]** activity to change the targeting dimension as you are building an audience. This activity shifts the axis depending on the data template and the input dimension. For example you switch from the "contracts" dimension to the "clients" dimension.

You can also use this activity to define the additional columns of the new target, and define data deduplication criteria.

To configure the **[!UICONTROL Change dimension]** activity, apply the following steps:

1. Select the new targeting dimension via the **[!UICONTROL Change dimension]** field.

   ![](assets/s_user_change_dimension_param1.png)

1. During dimension change, you can keep all elements or select those to be kept in output. In the following example, the max. number of duplicates is set to 2.

   ![](assets/s_user_change_dimension_limit.png)

   When you choose to keep only one record, a collection is displayed in the work schema: This collection represents all records that will not be targeted in the final result (since only one record is kept). Like all other collections, this one lets you calculate aggregates or recover information in columns.

   For example, if you change the **[!UICONTROL Customers]** dimension to the **[!UICONTROL Recipients]** dimension, it will be possible to target customers of a specific store, while adding the number of purchases made.

1. If you choose not to keep all this information, you can configure the duplicate management mode.

   ![](assets/s_user_change_dimension_param2.png)

   The blue arrows enable you to define the duplicate processing priority.

   In the example above, recipients will be deduplicated on their email address first, then on their account number if necessary.

1. The **[!UICONTROL Result]** tab lets you add additional information.

   For example, you can recover the county based on the zip code by using a **Substring** type function. To do this:

    * Click the **[!UICONTROL Add data...]** link and select **[!UICONTROL Data linked to the filtering dimension]**.
    
      ![](assets/wf_change-dimension_sample_01.png)

      >[!NOTE]
      >
      >For information on creating and managing additional columns, refer to [Add data](query.md#add-data).

    * Select the previous targeting dimension (before axis switch) and select the **[!UICONTROL Zip Code]** in the recipient's **[!UICONTROL Location]** sub-tree, then click **[!UICONTROL Edit expression]**.
    
      ![](assets/wf_change-dimension_sample_02.png)

    * Click **[!UICONTROL Advanced selection]** and choose **[!UICONTROL Edit the formula using an expression]**.
    
      ![](assets/wf_change-dimension_sample_03.png)

    * Use the functions offered in the list and specify the calculation to be performed.
    
      ![](assets/wf_change-dimension_sample_04.png)

    * Finally, enter the label of the column you have just created.
    
      ![](assets/wf_change-dimension_sample_05.png)

1. Execute the workflow to view the result of this configuration. Compare the data in the tables before and after the change dimension activity, and compare the structure of the workflow tables, as shown in the following examples:

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
