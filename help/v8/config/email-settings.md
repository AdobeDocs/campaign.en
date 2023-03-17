---
title: Campaign email channel settings
description: Campaign email channel settings
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
---
# Campaign email channel settings

## Email BCC {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

You can configure Adobe Campaign to keep a copy of emails sent from your platform.

Adobe Campaign itself does not manage archived files. It does enable you to send the messages of your choice to a dedicated BCC (blind carbon copy) email address, from where they can be processed and archived using an external system. The .eml files corresponding to the sent emails can then be transferred to a remote server, such as an SMTP email server.

>[!CAUTION]
>
>For privacy reasons, BCC emails must be processed by an archiving system capable of storing securely personally identifiable information (PII).

The archiving destination is the BCC email address of your choice, which will remain invisible to the delivery recipients.

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} to communicate the BCC email address to be used for archiving.

Once the BCC email address is defined, you must enable the dedicated option at the delivery level.

>[!CAUTION]
>
>When creating a new delivery or delivery template, **[!UICONTROL Email BCC]** is not enabled by default. You need to enable it manually in the email delivery or delivery template.


To do this, follow the steps below:

1. Go to **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, or **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Select the delivery of your choice or duplicate the out-of-the-box **[!UICONTROL Email delivery]** template, then select the duplicated template.
1. Click the **[!UICONTROL Properties]** button.
1. Select the **[!UICONTROL Delivery]** tab.
1. Check the **[!UICONTROL Email BCC]** option.

    ![](assets/email-bcc.png)

1. Select **[!UICONTROL Ok]**.

A copy of all sent messages for each delivery based on this template will be sent to the email BCC address which has been configured.

Note the following specificities and recommendations:

* You can only use one BCC email address.

* Make sure the BCC address has enough reception capacity to archive all the emails that are sent.

* Email BCC <!--with Enhanced MTA--> delivers to the BCC email address before delivering to the recipients, which can result in BCC messages being sent even though the original deliveries may have bounced. For more on bounces, see [Understand delivery failures](../send/delivery-failures.md).

* If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Learn more in Campaign Classic v7 documentation**

* [Select email format](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [Select character encoding](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [Set the bounce email address](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

* [Use email delivery templates](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}

* [Understand delivery failures](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}
