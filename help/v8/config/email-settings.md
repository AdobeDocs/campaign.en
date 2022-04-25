---
title: Campaign email channel settings
description: Campaign email channel settings
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
---
# Campaign email channel settings

## Email BCC

You can configure Adobe Campaign to keep a copy of emails sent from your platform.

Adobe Campaign itself does not manage archived files. It does enable you to send the messages of your choice to a dedicated BCC email address, from where they can be processed and archived using an external system. The .eml files corresponding to the sent emails can be transferred to a remote server, such as an SMTP email server.

>[!IMPORTANT]
>
>For privacy reasons, BCC emails must be processed by an archiving system capable of storing securely personally identifiable information (PII).

The archiving destination is the BCC (blind carbon copy) email address, invisible to the delivery recipients, that you must specify.

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to communicate the BCC email address to be used for archiving.

Once the BCC email address is configured, you must enable the option in the delivery template or in the delivery through the **Email BCC** option.

To do this, follow the steps below:

1. Go to **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]** or **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Select the delivery of your choice or duplicate the out-of-the-box **[!UICONTROL Email delivery]** template, then select the duplicated template.
1. Click the **[!UICONTROL Properties]** button.
1. Select the **[!UICONTROL Delivery]** tab.
1. Check the **[!UICONTROL Email BCC]** option.

    ![](assets/email-bcc.png)

1. Select **[!UICONTROL Ok]**.

A copy of all sent messages for each delivery based on this template will be sent to the email BCC address which has been configured.

Note the following:

* You can only use **one** BCC email address.

* Make sure the BCC address has enough reception capacity to archive all the emails that are sent.

* Email BCC with Enhanced MTA delivers to the BCC email address before delivering to the recipients, which can result in BCC messages being sent even though the original deliveries may have bounced. For more on bounces, see [Understanding delivery failures](../../delivery/using/understanding-delivery-failures.md).

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Related topics** in Campaign Classic v7 documentation:

* [Generate the mirror page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target="_blank"}

* [Select email format](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [Select character encoding](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [Set the bounce email address](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

* [Use email delivery templates](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}

* [Understand delivery failures](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}
