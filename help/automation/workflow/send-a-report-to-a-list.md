---
product: campaign
title: Send a report to a list
description: Learn how to send a report to a list with a workflow
feature: Workflows
---

# Send a report to a list{#send-a-report-to-a-list}

This use case details how to generate a monthly out-of-the-box **[!UICONTROL Tracking indicators]** report in PDF format and how to send it to a list of recipients.

![](assets/use_case_report_intro.png)

The main implementation steps for this use case are:

* Create a list of recipients for this report. [Learn more](#step-1--create-the-recipient-list). 
* Create a delivery template which creates a new delivery each time the workflow is executed. [Learn more](#step-2--create-the-delivery-template).
* Create a workflow which generates the report in PDF format and sends it to the list of recipients. [Learn more](#step-3--create-the-workflow)).

## Step 1: Create the recipient list {#step-1--create-the-recipient-list}

To create the list of targeted recipients, follow the steps below:

1. Browse to the **[!UICONTROL Profiles and targets]** tab, click the **[!UICONTROL Lists]** link.
1. Click the **[!UICONTROL Create]** button. 
1. Select **[!UICONTROL New list]** and create a new recipient list for the report to be sent to.

For more on creating lists, refer to [this section](../../v8/audiences/create-audiences.md).

## Step 2: Create the delivery template {#step-2--create-the-delivery-template}

To create the delivery template, follow the steps below:

1. Browse to the **[!UICONTROL Resources > Templates > Delivery templates]** node of the Adobe Campaign explorer and duplicate the **[!UICONTROL Email delivery]** built-in template.

   For more on creating a delivery template, refer to [this section](../../v8/send/create-templates.md).

1. Enter the template parameters: label, target (the list of previously created recipients), subject and content.

   Each time the workflow is executed, the **[!UICONTROL Tracking indicators]** report is updated as explained in [Step 3: Create the workflow](#step-3--creating-the-workflow)).

1. To include the latest version of the report in the delivery, you need to add a **[!UICONTROL Calculated attachment]**:

    * Click the **[!UICONTROL Attachments]** link and click the arrow next to the **[!UICONTROL Add]** button. Select **[!UICONTROL Calculated attachment...]**.
    
      ![](assets/use_case_report_4.png)

    * In the **[!UICONTROL Type]** drop-down list, select the latest option: **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**. 
    
      ![](assets/use_case_report_5.png)

      The value entered in the **[!UICONTROL Label]** field will not appear in the final delivery.
    
    * In the text zone, enter the access path and name of the file. 
    
      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >The path and name must be identical to those entered in the **[!UICONTROL JavaScript code]** type activity of the workflow, as explained in [Step 3: Create the workflow](#step-3--creating-the-workflow).

    * Select the **[!UICONTROL Advanced]** tab and check **[!UICONTROL Script the name of the file name displayed in the mails sent]**. In the text zone, enter the name of the attachment in the final delivery.
    
      ![](assets/use_case_report_6bis.png)

## Step 3: Create the workflow {#step-3--creating-the-workflow}

Create the following workflow for this use case. 

![](assets/use_case_report_8.png)

It uses three activities:

* A **[!UICONTROL Scheduler]** activity which executes the workflow once a month,
* A **[!UICONTROL JavaScript code]** activity which generates the report in PDF format,
* A **[!UICONTROL Delivery]** activity which references the previously created delivery template.

To build this workflow, follow the steps below:

1. Browse to the **[!UICONTROL Administration > Production > Technical workflows]** node of Campaign exploere and create a new folder to store your workflows.
1. Create a new workflow.

   ![](assets/use_case_report_7.png)

1. Start by adding a **[!UICONTROL Scheduler]** type activity and configure it so that the workflow executes on the first Monday of the month.

   ![](assets/use_case_report_9.png)

   For more on configuring the scheduler, refer to [Scheduler](scheduler.md).

1. Then add a **[!UICONTROL JavaScript code]** type activity.

   ![](assets/use_case_report_10.png)

   Enter the following code in the edit zone:
   
   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;

   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   with the following variables:

    * **var reportName**: enter the internal name of the report in double quotes. In this case, the internal name of the **Tracking indicator** report is "deliveryFeedback".
    * **var path**: enter the save path of the file ("tmp"), the name you want to give the file ("deliveryFeedback") and the file extension (".pdf"). In this case, we have used the internal name as the file name. Values need to be between double quotes and separated by the "+" character.

      >[!CAUTION]
      >
      >The file must be saved on the server. You must enter the same path and the same name as in the **[!UICONTROL General]** tab of the edit window for the calculated attachment, as detailed [here](#step-2--create-the-delivery-template)).

    * **var exportFormat**: enter the export format of the file ("PDF").
    * **var _ctx** (context): in this case, we are using the **[!UICONTROL Tracking indicators]** report in its global context.

1. Finish by adding a **[!UICONTROL Delivery]** activity with the following options:

   ![](assets/use_case_report_11.png)

    * **[!UICONTROL Delivery]**: select **[!UICONTROL New, created from a template]**, and select the delivery template created previously.
    * For the **[!UICONTROL Recipients]** and **[!UICONTROL Content]** fields, select **[!UICONTROL Specified in the delivery]**.
    * **[!UICONTROL Action to perform]**: select **[!UICONTROL Prepare and start]**. 
    * Un-check the **[!UICONTROL Generate an outbound transition]** and **[!UICONTROL Process errors]** options.

1. Save your changes and start the workflow. The message is sent to the list of recipient every first monday of the month, with the attached report.