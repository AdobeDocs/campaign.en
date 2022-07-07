---
title: Manage and automate processes with Adobe Campaign workflows
description: Get started with workflows
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
---
# Manage and automate processes

Configure Campaign to leverage powerful marketing campaign automation capabilities.

You can set up:

* Workflows
* Recurring campaigns
* End-to-end validation cycle
* Alerts
* Automatic report sending
* Triggered events

## Design and use workflows{#gs-ac-wf}

Use Adobe Campaign workflows to improve the speed and scale of every aspect of your marketing campaigns, from creating segments and preparing messages to delivery.

Learn how to design workflows in these [end-to-end use cases](#end-to-end-uc).

Learn more about workflows user interface and execution in Campaign Classic v7 documentation:

* [Get started with workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target="_blank"}

* [Workflow best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html){target="_blank"}

* [Built-in technical workfows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target="_blank"}

* [Monitor workflows execution](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [Build an audience in a marketing campaign workflow](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

## Workflow activities {#wf-activities}

Learn more about the available workflow activities in [this section](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

Workflow activities are grouped by category. The four activity categories are available:

<<<<<<< Updated upstream
* [Targeting activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target="_blank"}: Query, Read list, Enrichment, Union, and more
* [Flow control activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html){target="_blank"}: Scheduler, Fork, Alert, External signal, and more
* [Action activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target="_blank"}: Cross-channel deliveries, Javascript code, CRM activities, Update aggregate, and more
* [Event activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target="_blank"}: File transfer, Web download and more
=======
* [Targeting activities](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html): Query, Read list, Enrichment, Union, and more
* [Flow control activities](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html): Scheduler, Fork, Alert, External signal, and more
* [Action activities](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html): Cross-channel deliveries, Javascript code, CRM activities, Update aggregate, and more
* [Event activities](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html): File transfer, Web download and more
>>>>>>> Stashed changes

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

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.

## Manage virtual warehouses {#warehouse}

After creating your workflow, you can access additional options with the **[!UICONTROL Properties]** button for further configuration.

Learn more about **Workflow properties** in [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

From the **[!UICONTROL Execution]** tab of your workflow's **[!UICONTROL Properties]**, you can choose to link your workflow to different warehouses and optimize your workload management. For more information on **Warehouses**, refer to the [Snowflake documentation](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

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

Learn how to create a recurring campaign in [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html)


## Leverage trigger events

Use Campaign Transactional messaging to automate messages generated from events triggered from information systems. These transactional messages can be invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement or website account creation for instance. These messages can be sent individually or in batch via email, SMS or push notifications.

![](../assets/do-not-localize/glass.png) Learn more about transactional messaging capabilities in in [this section](../send/transactional.md).

Connect Adobe Campaign and Adobe Analytics to retrieve user actions and send near real-time personalized messages. 

![](../assets/do-not-localize/glass.png) Learn how to integrate Campaign with other solutions in [this section](../start/connect.md)


## Workflow end-to-end use cases{#end-to-end-uc}

In this section, you will find various use cases leveraging Campaign workflows capabilities.

### Deliveries {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

    
* [Send a birthday email](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html)

    This use case presents how to plan sending a recurring email to a list of recipients on the day of their birthday.

* [Load delivery content](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
    When your delivery content is available in an HTML file located on a remote server, you can easily load this content into Adobe Campaign deliveries.

* [Cross-channel delivery workflow](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
    Learn how to build a cross-channel delivery workflow. The objective is to segment an audience from the recipients of your database into different groups and send an email to the first group and a SMS to the other.

* [Email enrichment with custom date fields](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
    Learn how to send an email with custom data fields to profiles who celebrate their birthdays this month. The email will include a coupon valid one week before and after their birthday.

And these pages in Campaign v7 documentation: 

* [Automat content creation, edition and publishing](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target="_blank"}
    Learn how to automate the creation and delivery of a content block with Campaign Content Management add-on.

* [A/B testing](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target="_blank"}
    Learn how to compare two email delivery contents via a targeting workflow. The message and the text are identical in both deliveries: only the layout changes. The targeted population is divided into three: two test groups and the remaining population. A different version of the delivery is sent to each test group.

### Monitoring {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Send a report to a list](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
    Learn how to generate a monthly built-in Tracking indicators report in PDF format and send it to a list of Campaign operators.

* [Supervise your workflows](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
    Learn how to create a workflow that lets you monitor the status of a set of workflows that are “paused”, “stopped” or “with errors”.

* [Send personalized alerts to operators](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
    Learn how to send an alert to an operator that will contain the name of profiles who opened a newsletter but did not click the link it contains.

### Data management {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinate data updates](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
    Learn how to check that the update process has ended before executing another update operation. To do this, we will set up an instance variable, and let the workflow test if the instance is running to decide whether to continue the execution of the workflow and perform the update.

* [Create a summary list](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
    Learn how to create a workflow which, after collecting files and following several enrichments, lets you create a summary list. The example is based on a list of contacts who made purchases in a store.

* [Enrich data](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html)
    Learn how to send personalized deliveries to profiles who took part in the latest competition depending on their score.

* [Use aggregates](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
    Learn how to identify the last recipients added to the database.

* [Quarterly list update using an incremental query](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
    Learn how to use an incremental query to automatically update a recipient list.

* [Set up a recurring import workflow](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
    Learn how to design a workflow that can be reused for importing profiles coming from a CRM in the Adobe Campaign database. 

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Query the recipient table](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
    Learn how to recover the names and emails of recipients whose email domain is “orange.co.uk” and who don’t live in London.

* [Query delivery information](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
    Learn how to define queries on delivery information to retrieve profile's behavior.

* [Compute aggregates](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
    Learn how to count the number of profiles living in London, according to gender.
    
* [Query using a many-to-many-relationship](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
    Learn how to find profiles not contacted during the last 7 days. 

* [Call an instance variable in a query](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
    Learn how to use an instance variable to compute dynamically the split percentage to apply on a population.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

