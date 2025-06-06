---
product: campaign
title: Start and end
description: Learn more about Start and End workflow activities
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
---
# Start and end{#start-and-end}



The **[!UICONTROL Start]** and **[!UICONTROL End]** activities allow you to graphically mark the start and end of a workflow. These activities have no functional impact and are therefore optional.

* **[!UICONTROL Start]**

  Executing a workflow starts with activities without an inbound transition and Start-type activities.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL End]**

  You can configure the **[!UICONTROL End]** activity to interrupt all tasks that are in progress. To do this, double-click the activity to display its properties, and check the appropriate option.

  ![](assets/s_user_segmentation_end.png)

  The data in the worktable is deleted automatically when the end activity is enabled. If this isn't necessary, and to avoid unnecessary loads, you can choose to disable the transition at the last activity output. For example, at a delivery output, if no process is scheduled, uncheck the relevant option as shown below:

  ![](assets/s_advuser_delivery_option_no_output.png)
