---
title: Send SMS with Adobe Campaign
description: Get started with SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
---
# Get started with SMS {#gs-sms-channel}

Adobe Campaign allows you to deliver personalized SMS on mobiles.

For SMS messages, you can create, modify, and personalize messages in text format only. You can also preview your SMS messages before they are sent.

>[!NOTE]
>
>You can also use Adobe Campaign to send [LINE](../../send/line.md) messages, with text and/or images and links.

To deliver SMS to a mobile phone with Adobe Campaign, you need:

* An external account configured on the **[!UICONTROL Mobile (SMS)]** channel or on the **[!UICONTROL LINE]** channel. 
* An SMS delivery template that is correctly linked to this external account.

You can see in this documentation the steps to configure, send and monitor an SMS delivery:

* **Configure SMS channel**

First, you need to configure the SMS channel on your [mid-sourcing infrastructure](sms-mid-sourcing.md). 

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

For this configuration, you need to understand the [SMPP external account parameters](smpp-external-account.md) and the [SMS channel characteristics](sms-channel.md).

After this set up, check your [SMPP connection and know how to troubleshoot it if needed](smpp-connection.md).

* **Create your first SMS delivery**

To begin the configuration of your SMS delivery: 

1. Create your delivery, and fill in the [SMS delivery settings](sms-delivery-settings.md),

1. [Define the content](sms-content.md) of your delivery,

1. [Select the audience](sms-audience.md).

Steps to define an audience are detailed on [this page](../../audiences/create-audiences.md).

* **Validate and send SMS** 

After the creation of your delivery:

1. [Send proofs](sms-proofs.md) to validate the rendering and the content,

1. Then, [send to the final audience](sms-send.md).

* **Monitor and track SMS** 

After the send, [learn how to monitor and track your SMS](sms-monitor.md).
