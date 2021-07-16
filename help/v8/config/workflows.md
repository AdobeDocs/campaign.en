---
product: Adobe Campaign
title: Manage and automate processes with Adobe Campaign workflows
description: Get started with workflows
feature: Overview
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

↗️ [Get started with workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows){target="_blank"}

↗️ [Workflow best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html){target="_blank"}

↗️ [Built-in technical workfows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html){target="_blank"}

↗️ [Monitor workflows execution](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html){target="_blank"}

↗️  [Build an audience in a marketing campaign workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target="_blank"}

## Workflow activities {#wf-activities}

↗️ Learn more about the available workflow activities [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-activities.html){target="_blank"}

Workflow activities are grouped by category. The four activity categories are available:

* [Targeting activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html){target="_blank"}: Query, Read list, Enrichment, Union, and more
* [Flow control activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html){target="_blank"}: Scheduler, Fork, Alert, External signal, and more
* [Action activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target="_blank"}: Cross-channel deliveries, Javascript code, CRM activities, Update aggregate, and more
* [Event activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html){target="_blank"}: File transfer, Web download and more

### Change Data Source Activity {#change-data-source-activity}

There are two goals here:

Provide a new workflow activity allowing to "change" the "data-source" of workflow working table (Technically it will create a new working table on the new data-source and perform a copy of the input data to this new working table)
In V8, this activity allows the possibility to perform large and efficient unitary operations on working table data by moving the worktable from snowflake to postgresql.
Simplify the understanding of the location (data-source) of the workflow working table
Display Target: Add the data Source information
Javascript Activity: Add a warning at execution when queryDef , write are used directly on the Snowflake database

 A new workflow activity is introduced. The <b>Change Data Source</b> activity allows you to change the data source of a workflow working table. This provides enhanced flexibility in managing data across different data sources (FDA, FFDA & local database)
An Adobe Campaign workflow handles data thanks to what we call a Working table (aka temporary table). As the workflow executes, working tables are sharing data across workflow activities.
By default, Working Tables are created on the same database than the source of the data we query on.
Example: With V8, main profiles table is now stored on Cloud database directly. So querying on Profiles table will create a working table on Cloud database as well.
Sometimes it could make sense to move the working table to another data source in order to perform specific operation(s)
Example :
- I query on my Products List which is stored on the Cloud Database.
- A new working table is then created on Cloud database and this contains the result of my query.
- Now I need to run a Javascript Activity that performs unitary operations on this working table.
- I know this is not recommended to perform such unitary operations on the Cloud Database directly.
- Then I will first move the working table from Cloud Database to the local Postgres Database.
- I am now able to run my script on top of the local Postgres database which is more efficient with unitary operations.
This was just an example and there are many other use use cases that benefit from this new <b>Change Data Source</b> activity.


## Set up recurring campaigns

Design recurring workflow and create a new delivery instance each time the workflow is executed. For example, if your workflow is designed to run once a week, that would result in 52 Deliveries after one year. This also means that logs will be separated by each delivery instance.

↗️ Learn how to create a recurring campaign in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns){target="_blank"}


## Leverage trigger events

Use Campaign Transactional messaging to automate messages generated from events triggered from information systems. These transactional messages can be invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement or website account creation for instance. These messages can be sent individually or in batch via email, SMS or push notifications.

💡 Learn more about transactional messaging capabilities in in [this section](../send/transactional.md).

Connect Adobe Campaign and Adobe Analytics to retrieve user actions and send near real-time personalized messages. 

💡 Learn how to integrate Campaign with other solutions in [this section](../start/connect.md)


## Workflow end-to-end use cases{#end-to-end-uc}

In this section, you will find various use cases leveraging Campaign workflows capabilities. These use cases are built in Adobe Campaign Classic v7 and apply to Adobe Campaign v8.

### Deliveries {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B testing](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target="_blank"}

    Learn how to compare two email delivery contents via a targeting workflow. The message and the text are identical in both deliveries: only the layout changes. The targeted population is divided into three: two test groups and the remaining population. A different version of the delivery is sent to each test group.
    
* [Sending a birthday email](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"}

    This use case presents how to plan sending a recurring email to a list of recipients on the day of their birthday.

* [Loading delivery content](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html){target="_blank"}
    When your delivery content is available in an HTML file located on a remote server, you can easily load this content into Adobe Campaign deliveries.

* [Cross-channel delivery workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html){target="_blank"}

    Learn how to build a cross-channel delivery workflow. The objective is to segment an audience from the recipients of your database into different groups and send an email to the first group and a SMS to the other.

* [Email enrichment with custom date fields](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html){target="_blank"}

    Learn how to send an email with custom data fields to profiles who celebrate their birthdays this month. The email will include a coupon valid one week before and after their birthday.

* [Automating content creation, edition and publishing](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target="_blank"}

    Learn how to automate the creation and delivery of a content block with Campaign Content Management add-on.


### Monitoring {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Send a report to a list](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html){target="_blank"}

    Learn how to generate a monthly built-in Tracking indicators report in PDF format and send it to a list of Campaign operators.

* [Supervise your workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html){target="_blank"}

    Learn how to create a workflow that lets you monitor the status of a set of workflows that are “paused”, “stopped” or “with errors”.

* [Send personalized alerts to operators](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html){target="_blank"}

    Learn how to send an alert to an operator that will contain the name of profiles who opened a newsletter but did not click the link it contains.

### Data management {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinate data updates](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html){target="_blank"}

    Learn how to check that the update process has ended before executing another update operation. To do this, we will set up an instance variable, and let the workflow test if the instance is running to decide whether or not to continue the execution of the workflow and perform the update.

* [Create a summary list](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html){target="_blank"}

    Learn how to create a workflow which, after collecting files and following several enrichments, lets you create a summary list. The example is based on a list of contacts who made purchases in a store.

* [Enrich data](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html){target="_blank"}

    Learn how to send personalized deliveries to profiles who took part in the latest competition depending on their score.

* [Use aggregates](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html){target="_blank"}

    Learn how to identify the last recipients added to the database.

* [Quarterly list update using an incremental query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html){target="_blank"}

    Learn how to use an incremental query to automatically update a recipient list.

* [Set up a recurring import workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

    Learn how to design a workflow that can be reused for importing profiles coming from a CRM in the Adobe Campaign database. 

### Targeting {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Query the recipient table](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html){target="_blank"}

    Learn how to recover the names and emails of recipients whose email domain is “orange.co.uk” and who don’t live in London.

* [Query delivery information](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html){target="_blank"}

    Learn how to define queries on delivery information to retrieve profile's behaviour.

* [Compute aggregates](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html){target="_blank"}

    Learn how to count the number of profiles living in London, according to gender.
    
* [Query using a many-to-many-relationship](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html){target="_blank"}

    Learn how to find profiles not contacted during the last 7 days. 

* [Call an instance variable in a query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example){target="_blank"}

    Learn how to use an instance variable to compute dynamically the split percentage to apply on a population.
    