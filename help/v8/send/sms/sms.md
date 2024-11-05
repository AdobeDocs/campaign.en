---
title: Send SMS with Adobe Campaign
description: Get started with SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
---
# Get started with SMS {#gs-sms-channel}

Use Adobe Campaign to send personalized SMS messages.

>[!NOTE]
>
>Adobe Campaign also lets you submit push notifications on mobiles, via its **Adobe Campaign Mobile App Channel (NMAC)** option. Learn more in [this section](../push.md).

The simplicity and ease of use of SMS make it a very valuable communication channel in addition to its robustness and unrivaled compatibility over billions of terminals. 

There are 2 main ways to send an SMS:

* Send it manually from a phone. That is the usual way you use to communicate directly between people.
* Send it from the internet. That is the way Adobe Campaign uses to send messages. For that, you need a SMS service provider that makes a bridge from the internet to the mobile network.

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
