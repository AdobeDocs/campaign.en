---
title: Send SMS with Adobe Campaign
description: Get started with SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
---
# Get started with SMS

Use Adobe Campaign to send personalized SMS messages.

>[!IMPORTANT]
>
>This documentation is for Adobe Campaign v8.7.2 and later.
For older versions, please read the [Campaign Classic v7 documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>Adobe Campaign also lets you submit push notifications on mobiles, via its **Adobe Campaign Mobile App Channel (NMAC)** option. Learn more in [this section](../push.md).

The simplicity and ease of use of SMS make it a very valuable communication channel in addition to its robustness and unrivaled compatibility over billions of terminals. 

There are 2 main ways to send an SMS:

* Send it manually from a phone. That is the usual way you use to communicate directly between people.
* Send it from the internet. That is the way Adobe Campaign uses to send messages. For that, you need a SMS service provider that makes a bridge from the internet to the mobile network.

You can see in this documentation the steps to configure, send and monitor an SMS delivery :

* **Configure SMS channel**

First, you need to configure the SMS channel. 

The steps depend on the platform : either you have [a standalone instance](sms/sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms/sms-mid-sourcing.md).

For this configuration, you need to understand the [SMPP external account parameters](sms/smpp-external-account.md) and the [SMS channel characteristics](sms/sms-channel.md).

After this set up, check your [SMPP connection and know how to troubleshoot it if needed](sms/smpp-connection.md).

* **Create your first SMS delivery**

To begin the configuration of your SMS delivery : 

1. Create your delivery, and fill in the [SMS delivery settings](sms/sms-delivery-settings.md),

1. [Define the content](sms/sms-content.md) of your delivery,

1. [Select the audience](sms/sms-audience.md).

Steps to define an audience are detailed on [this page](../start/audiences.md).

* **Validate and send SMS** 

After the creation of your delivery :

1. [Send proofs](sms/sms-proofs.md) to validate the rendering and the content,

1. Then, [send to the final audience](sms/sms-send.md).

* **Monitor and track SMS** 

After the send, [learn how to monitor and track your SMS](sms/sms-monitor.md).

* **Process inbound message** 
    
Understand what is the [process for inbound messages](sms/sms-inbound.md).
