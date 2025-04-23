---
product: campaign
title: Create recurring and periodic campaigns
description: Learn how to create and execute recurring and periodic campaigns
feature: Campaigns, Cross Channel Orchestration, Programs
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 68c5b903-5043-4e74-b3f6-90a7f2fb3b9a
---
# Recurring and periodic campaigns {#recurring-and-periodic-campaigns}

A **recurring campaign** is a campaign based on a specific template, whose workflows are configured to be executed according to an associated schedule. The targeting is duplicated on each execution and the various processes and target populations are tracked.  Once configured, recurring campaigns automatically create a new workflow (by duplicating the workflow template) and run it. For example, if you need to send monthly reminder to an audience segment, configure a recurring campaign so that at the beginning of each year, it creates 12 workflows, one for each month. [Learn more](#create-a-recurring-campaign)

A **periodic campaign** is a campaign based on a specific template that lets you create campaign instances based on an execution schedule. Campaign instances are created automatically based on a periodic campaign template, depending on the frequency defined in the template schedule. [Learn more](#create-a-periodic-campaign)

## Create a recurring campaign {#create-a-recurring-campaign}

Recurring campaigns are created from a specific template defining the workflow template to be executed and the execution schedule.

### Create a template for recurring campaigns {#create-the-campaign-template}

To create a template for recurring campaigns, follow the steps below:

1. Open Campaign explorer and browse to **[!UICONTROL Resources > Templates > Campaign templates]**.
1. Duplicate the built-in **[!UICONTROL Recurring campaign]** template.
    ![](assets/recurring-campaign-duplicate.png)
1. Enter the name of the template and the duration of the campaign.
1. For this type of campaign, a **[!UICONTROL Schedule]** tab is added in order to create the template execution schedule. Use this tab to define the execution dates of the campaigns based on this template.
  ![](assets/recurring-campaign-schedule.png)

    The configuration mode of the execution schedule coincides with the **[!UICONTROL Scheduler]** object of the Workflow. [Learn more](../workflow/scheduler.md).

    >[!CAUTION]
    >
    >Execution schedule configuration must be performed carefully. Recurring campaigns duplicate the workflow(s) of their template depending on the specified schedule. This operation can overload your database. 

1. Specify a value in the **[!UICONTROL Create in advance for]** field in order to create the corresponding workflows for the period indicated.
1. In the **[!UICONTROL Targeting and workflows]** tab, design the workflow template to be used in campaigns based on this template. This workflow typocally contains the targeting parameters and one or more deliveries.

    >[!NOTE]
    >
    >This workflow must be saved as a recurring workflow template. To do this, edit the workflow properties and select the **[!UICONTROL Recurring workflow template]** option in the **[!UICONTROL Execution]** tab.

    ![](assets/recurring-campaign-wf-properties.png)

### Create the recurring campaign {#create-the-recurring-campaign}

To create the recurring campaign and execute its workflows according to the schedule defined in the template, you must:

1. Create a new campaign based on your recurring campaign template.
1. Fill in the workflow execution schedule, in the **[!UICONTROL Schedule]** tab. The campaign schedule lets you enter an automatic workflow creation or execution start date for each line.

   For each line, you can add the following additional options:

    * Enable the **[!UICONTROL To be approved]** option to force the delivery approval requests in the workflow.
    * Enable the **[!UICONTROL To be started]** option to start the workflow when the start date has been reached.

   The **[!UICONTROL Create in advance for]** field lets you create all the workflows covering the period entered.

   Upon execution of the **[!UICONTROL Jobs on campaigns]** workflow, the dedicated workflows are created based on the occurrences defined in the campaign schedule. A workflow is thus created for each execution date.

1. Recurring workflows are created automatically from the workflow template present in the campaign. They are visible from the **[!UICONTROL Targeting and workflows]** tab of the campaign. 

   ![](assets/recurring-wf-created.png)

   The label of a recurring workflow instance consists of its template label and the workflow number, with the # character in between.

   Workflows created from the schedule are automatically associated with it in the **[!UICONTROL Workflow]** column of the **[!UICONTROL Schedule]** tab. 

   ![](assets/recurring-wf-schedule-executed.png)

   Each workflow can be edited from this tab.

   >[!NOTE]
   >
   >The start date of the schedule line associated with the workflow is available from a variable of the workflow with the following syntax:   
   >`$date(instance/vars/@startPlanningDate)`

## Create a periodic campaign {#create-a-periodic-campaign}

A periodic campaign is a campaign based on a specific template that lets you create campaign instances based on an execution schedule. Campaign instances are created automatically based on a periodic campaign template, depending on the frequency defined in the template schedule.

### Create the campaign template {#create-the-campaign-template-1}

1. Open Campaign explorer and browse to **[!UICONTROL Resources > Templates > Campaign templates]**.
1. Duplicate the built-in **[!UICONTROL Periodic campaign]** template.
1. Enter the properties of the template.

     >[!NOTE]
     >
     >The operator whom the template is assigned must have the appropriate permissions to create campaigns in the selected program.

1. Create the workflow associated with this template. This worflow is duplicated in every periodic campaign created by the template.

      >[!NOTE]
      >
      >This workflow is a workflow template. It cannot be executed from the campaign template.

1. Complete its execution schedule as for a recurring campaign template: click the **[!UICONTROL Add]** button and define the start and end dates, or fill in the execution schedule via the link.

      >[!CAUTION]
      >
      >Periodic campaign templates create new campaigns according to the schedule defined above. It must therefore be completed carefully, to avoid overloading the Adobe Campaign database.

1. Once the execution start date is reached, the matching campaign is created automatically. It takes on all the characteristics of its template.

    Each campaign can be edited via the template schedule.

    Each periodic campaign contains the same elements. Once created, it is managed as a standard campaign.
