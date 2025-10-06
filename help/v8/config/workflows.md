---
title: Manage and automate processes with Adobe Campaign workflows
description: Get started with workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
---
# Get started with workflows{#gs-with-workflows}

Configure Campaign to leverage powerful marketing campaign automation capabilities.

You can set up:

* Workflows
* Recurring campaigns
* End-to-end validation cycle
* Alerts
* Automatic report sending
* Triggered events

>[!NOTE]
>
>Adobe Campaign Web User interface comes with a reimagined canvas for workflows, allowing to create more dynamic and personalized customer journeys. To learn more about Workflows for Web UI, please refer to [Adobe Campaign Web UI documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Design and use workflows {#gs-ac-wf}

Use Adobe Campaign workflows to improve the speed and scale of every aspect of your marketing campaigns, from creating segments and preparing messages to delivery.

Learn more about workflows user interface and execution in these pages:

* [Get started with workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"}

* [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

* [Built-in technical workfows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

* [Monitor workflows execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

* [Build an audience in a marketing campaign workflow](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"}

## Workflow activities {#wf-activities}

Learn more about the available workflow activities in [this section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html){target="_blank"}

Workflow activities are grouped by category. The four activity categories are available:

* [Targeting activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}: Query, Read list, Enrichment, Union, and more
* [Flow control activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}: Scheduler, Fork, Alert, External signal, and more
* [Action activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}: Cross-channel deliveries, Javascript code, CRM activities, Update aggregate, and more
* [Event activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}: File transfer, Web download and more

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## Manage virtual warehouses {#warehouse}

After creating your workflow, you can access additional options with the **[!UICONTROL Properties]** button for further configuration.

Learn more about **Workflow properties** in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html){target="_blank"}.

From the **[!UICONTROL Execution]** tab of your workflow's **[!UICONTROL Properties]**, you can choose to link your workflow to different warehouses and optimize your workload management. For more information on **Warehouses**, refer to the [Snowflake documentation](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Depending on your workflow's purpose, you can choose between the following three warehouses from the **[!UICONTROL Warehouse]** drop-down:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: set by default when creating a new workflow.

* **[!UICONTROL Import / Export]**: should be set with import or export workflows to optimize your activities' performance.

* **[!UICONTROL Campaign Burst]**: should be set with campaign or deliveries workflows to optimize your deliveries processing time.

>[!NOTE]
>
>The **[!UICONTROL System]** warehouse is only set for built-in workflows.

## Set up recurring campaigns

Design recurring workflow and create a new delivery instance each time the workflow is executed. For example, if your workflow is designed to run once a week, that would result in 52 Deliveries after one year. This also means that logs will be separated by each delivery instance.

Learn how to create a recurring campaign in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html){target="_blank"}.


## Leverage trigger events

Use Campaign Transactional messaging to automate messages generated from events triggered from information systems. These transactional messages can be invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement or website account creation for instance. These messages can be sent individually or in batch via email, SMS or push notifications.

Learn more about transactional messaging capabilities in in [this section](../send/transactional.md).

Connect Adobe Campaign and Adobe Analytics to retrieve user actions and send near real-time personalized messages. 

Learn how to integrate Campaign with other solutions in [this section](../start/connect.md)


## Workflow end-to-end use cases{#end-to-end-uc}

Learn through use cases leveraging Campaign workflows capabilities [in this section](../../automation/workflow/workflow-use-cases.md).
