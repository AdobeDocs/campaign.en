---
title: Send direct mails with Adobe Campaign
description: Get started with direct mail in Campaign
feature: Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
---
# Create direct mail deliveries

Direct mail deliveries let you generate an extraction file which contains data on the target population. You can then share this file with the provider who will deliver messages to the target populations.

Steps to generate the file are:

1. [Create the delivery](#creating-a-direct-mail-delivery)
1. [Define the audience](#defining-the-direct-mail-audience)
1. [Define the content of the file](#defining-the-direct-mail-content)
1. [Validate the delivery](#validating)
1. [Start the  delivery](#start-delivery)

## Create the delivery{#creating-a-direct-mail-delivery}

Create a direct mail delivery based on the template. You can duplicate and configure the **[!UICONTROL Deliver by direct mail (paper)]** built-in template.

To create a new direct mail delivery, follow the steps below:

>[!NOTE]
>
>Global concepts on delivery creation are presented in [this section](../start/create-message.md).

1. Create a new delivery, for example from the Delivery dashboard.
1. Select the delivery template **Deliver by direct mail (paper)**.

   ![](assets/direct_mail.png)

1. Identify your delivery with a label, code, and description. For more on this, refer to [this section](../start/create-message.md#create-the-delivery).
1. Click **Continue** to confirm this information and display the message configuration window.

## Define the audience{#defining-the-direct-mail-audience}

The recipient profiles must contain at least their names and postal addresses.

Postal addresses are calculated fields. An address can contain up to six lines by default: the first contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city. The definition of the default calculated postalAddress field can be reviewed in the nms:recipient schema.

An address is considered to be complete if the name, ZIP/Postal code field, and town/city fields are not empty. Any recipients with incomplete addresses will be excluded from direct mail deliveries. 

Learn more in [this section](../start/create-message.md#target-population).

## Define the content of the file{#defining-the-direct-mail-content}

Use the extraction wizard to define the information (columns) to be exported into the output file. 

The name of the file which contains the extracted data is defined in the **[!UICONTROL File]** field. The button to the right of the field lets you use personalization fields to create the file name.

By default, the extraction file is created and stored on the server. You can save it on your computer. To do this, check the **[!UICONTROL Download the generated file after the analysis of the delivery]**. In this case, you need to indicate the access path to the local storage directory as well as the file name.

![](assets/s_ncs_user_mail_delivery_local_file.png)

For a direct mail delivery, the content of the extraction is defined in **[!UICONTROL Edit the extraction file format...]** link.

![](assets/s_ncs_user_mail_delivery_format_link.png)

This link lets you access the extraction assistant and define the information (columns) to be exported into the output file.

![](assets/s_ncs_user_mail_delivery_format_wz.png)

You can insert a personalized URL into the extraction file. For more on this, refer to the Adobe Campaign Classic [documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/publishing-a-web-form.html){target="_blank"}.

>[!NOTE]
>
>This assistant includes the steps of the export assistant detailed the Adobe Campaign Classic [documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-export-jobs.html){target="_blank"}..

## Validate the delivery{#validating}

Check the result of the analysis and the content of the output file. 

In the context of a marketing campaign, on the extraction date, the extraction file is created. You can view the content of the extracted file, approve it, or change the format and re-launch the extraction if needed. Once the file has been approved, you can send the notification e-mail to the router. Learn more in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"}.

Global concepts when validating a delivery are presented in [this section](../start/create-message.md#validate-the-delivery).

The output file of a direct mail delivery is generated during the delivery analysis. The file's content depends on the selected output columns (refer to this [section file](#defining-the-direct-mail-content)).

>[!NOTE]
>
>The analysis phase is detailed in this [section](delivery-analysis.md).

During the analysis phase, the file is generated but information concerning recipients (i.e. delivery logs) is not updated. You can therefore cancel this job without running any risks.

Check the result of the analysis and the content of the output file before clicking **[!UICONTROL Confirm delivery]**. A confirmation message lets you launch the delivery.

The send confirmation starts the data extraction in the specified file.

![](assets/s_ncs_user_postal_del_send_confirm_postal.png)

You can then close the assistant and look at the delivery logs via the **[!UICONTROL Delivery]** tab, accessible via the delivery details.

You can configure the delivery logs retrieval mode from the **[!UICONTROL Analysis]** tab of the delivery properties.

There are two modes:

* **[!UICONTROL Messages are considered sent after validation]** (default mode): in this function mode, all broadlogs are updated when the operator confirms the send (their status passes from 'Pending delivery' to 'Sent') and the delivery is automatically set to **[!UICONTROL Finished]**.
* **[!UICONTROL A file of results determines the messages that are sent and those that have failed]** : this mode allows you to update the broadlogs via an external file sent by the service provider. In this case, a workflow to process this information needs to be used in order to update the broadlog status.

  >[!NOTE]
  >
  >In this case, the delivery's status also needs to be changed to **[!UICONTROL Finished]** by the user as soon as the broadlogs are updated.

## Start the delivery{#start-delivery}

Once you validated the extraction file, click **Confirm delivery** a confirmation message lets you launch the delivery.

The confirmation starts the data extraction in the specified file.

In the context of a marketing campaign, when all approvals have been granted, the extraction files are created via a special workflow which, in a default configuration, starts automatically when a direct mail delivery is pending extraction. Learn more in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html){target="_blank"}.
