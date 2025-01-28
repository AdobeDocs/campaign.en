---
title: Send a copy of your messages to a BCC address
description: Learn how to activate email BCC in Adobe Campaign
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
---
# Send a copy of your messages to a BCC address {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## About email BCC {#gs-bcc}

You can configure Adobe Campaign to keep a copy of emails sent from your platform. This option allow you to send messages a dedicated BCC (Blind Carbon Copy) email address, from where they can be processed and archived using an external system.

>[!CAUTION]
>
>For privacy reasons, BCC emails must be processed by an archiving system capable of storing securely personally identifiable information (PII).

Adobe Campaign itself does not manage archived files. The .eml files corresponding to the sent emails can then be transferred to a remote server, such as an SMTP email server.

The archiving destination is the BCC email address of your choice, which will remain invisible to the delivery recipients. Once the BCC email address is defined, you must enable the dedicated option at the [delivery template](create-templates.md) level. 

>[!NOTE]
>
>As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} to communicate the BCC email address to be used for archiving.

## Enable email BCC {#enable-bcc}

To enable BCC for a specific [delivery template](create-templates.md), follow the steps below:

1. From Campaign explorer, browse to the delivery templates folder. By default, delivery templates are stored into the **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** folder. 
1. Edit the delivery template to update with BCC.
1. Click the **[!UICONTROL Properties]** button.
1. From the **[!UICONTROL Delivery]** tab, check the **[!UICONTROL Email BCC]** option.

    ![](assets/email-bcc.png)

1. Click **[!UICONTROL Ok]** to confirm.

A copy of all sent messages for each delivery based on this template will be sent to the email BCC address which has been configured for your platform.

## Guardrails and recommendations {#recommendations-bcc}

When using email BCC with Adobe Campaign, the following guardrails and recommendations apply:

* You can only use one BCC email address.

* Make sure the BCC address has enough reception capacity to archive all the emails that are sent.

* Email BCC <!--with Enhanced MTA--> delivers to the BCC email address before delivering to the recipients, which can result in BCC messages being sent even though the original deliveries may have bounced. For more on bounces, see [Understand delivery failures](delivery-failures.md).

* Emails sent to the BCC address should not be opened and clicked through, as these activities are be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, can cause miscalculations.

<!--Only successfully sent emails are taken in account, bounces are not.-->
