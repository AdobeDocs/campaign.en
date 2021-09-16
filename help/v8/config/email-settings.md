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

>[!NOTE]
>Email BCC capability is optional. Please check your license agreement.

Adobe Campaign itself does not manage archived files. It does enable you to send the messages of your choice to a dedicated address, from where they can be processed and archived using an external system.

To do this, .eml files corresponding to the sent emails are transferred to a remote server, such as an SMTP email server. The archiving destination is a BCC email address (invisible to the delivery recipients) that you must specify.

Note that:

* You can only use **one** BCC email address.

* Only successfully sent emails are taken in account, bounces are not.

💬 As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to activate Email BCC in Campaign. The BCC email address of your choice must be provided to the Adobe team who will configure it for you.

Once email BCC is configured, make sure the feature is enabled in the delivery template or in the delivery through the **Email BCC** option. 

![](assets/email-bcc.png)


**Related topics** in Campaign Classic v7 documentation:


↗️ [Generate the mirror page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target="_blank"}

↗️ [Select email format](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

↗️ [Select character encoding](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

↗️ [Set the bounce email address](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

↗️ [Use email delivery templates](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}

↗️ [Understand delivery failures](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}
