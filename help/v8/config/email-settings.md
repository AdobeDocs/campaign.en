---
solution: Campaign
product: Adobe Campaign
title: Campaign email channel settings
description: Campaign email channel settings
feature: Overview
role: Data Engineer
level: Beginner
---
# Campaign email channel settings

## Email BCC

You can configure Adobe Campaign to keep a copy of emails sent from your platform.

However, Adobe Campaign itself does not manage archived files. It does enable you to send the messages of your choice to a dedicated address, from where they can be processed and archived using an external system.

To do this, .eml files corresponding to the sent emails are transferred to a remote server, such as an SMTP email server. The archiving destination is a BCC email address (invisible to the delivery recipients) that you must specify.

>[!NOTE]
>
>* You can only use one BCC email address.
>
>* Only successfully sent emails are taken in account, bounces are not.
>

Once email BCC is configured, make sure the feature is enabled in the delivery template or in the delivery through the **Email BCC** option. 

:arrow_upper_right: For more on this, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**Note**: Email BCC capability is optional. Please check your license agreement.

:speech_balloon: As a Managed Cloud Services user, [contact Adobe](../start/support.md#support) to activate Email BCC in Campaign. The BCC email address of your choice must be provided to the Adobe team who will configure it for you.