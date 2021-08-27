---
product: campaign
title: Get started with deliveries
description: Create deliveries to send personalized messages on different channels.
audience: delivery
content-type: reference
topic-tags: about-deliveries-and-channels
exl-id: 92b5e013-b619-4f0b-b0b1-1fc2e653ceac
---
# Get started with deliveries{#communication-channels}

![](../../assets/common.svg)

With Adobe Campaign, you can send cross-channel campaigns including emails, SMS, LINE messages, Push notifications and direct mails, and measure their effectiveness using various dedicated [reports](../../reporting/using/delivery-reports.md). These messages are designed and sent though deliveries, and can be personalized for each recipient.

Core functionalities include targeting, definition and personalization of messages, execution of communications, and the associated operational reports. The main functional access point is the delivery wizard. This access point leads to multiple capabilities covered by Adobe Campaign.

Delivery sending can be automated by preparing a delivery and/or sending it in the process of a workflow. For more on delivery-type activities in workflows, refer to [this section](../../workflow/using/about-action-activities.md).

Adobe Campaign offers the following delivery channels:

1. **Email channel**: email deliveries let you send personalized emails to the target population. [Learn more](#email-deliveries).
1. **Direct mail channel**: direct mail deliveries let you generate an extraction file which contains data on the target population. [Learn more](direct/about-direct-mail-channel.md).
1. **Mobile channel**: deliveries on mobile channels let you send personalized SMS or LINE messages to the target population. [Learn more](#mobile-deliveries).
1. **Mobile application channel**: mobile app deliveries let you send notifications to iOS and Android systems. [Learn more](#push-notifications).

Other channels are described on [this section](#other-channels).

>[!NOTE]
>
>Available channels depend on your contract. Check your license agreement.

## Email deliveries {#email-deliveries}

The [Email channel](email/email.md) is one of the core channels in Adobe Campaign, allowing you to schedule and send personalized emails to specific audiences.

You can send different types of emails:

* Single-send emails: emails that you can send once to a defined target. They are usually used to promote a specific content that would be prepared and sent only once (newsletter, promotional email, etc.).
* Recurring emails: in a campaign, send the same email regularly and aggregate each send and its reports on a periodic basis. The same email is sent, but usually to a different target, based on the eligible target for the day of the send. A common example is a birthday email. [Learn more](#recurring-delivery).
* Transactional emails: unitary emails that are triggered based on your customers' behavior. 
   Learn more in these sections: 
   * [Transactional messaging in Campaign Classic v7](../../../v7/message-center/using/about-transactional-messaging.md) 
   * [Transactional messaging in Campaign v8](../../../v8/send/transactional.md)

To learn about delivery usage and recommendations, consult Campaign [Delivery best practices](delivery-best-practices.md).

For more on the different types of deliveries, refer to [this section](#types-of-deliveries).

## Mobile deliveries {#mobile-deliveries}

Adobe Campaign allows you to deliver [SMS](sms/sms.md) and [LINE](line-channel.md) messages on mobiles.

For SMS messages, you can create, modify, and personalize messages in text format only. You can also preview your SMS messages before they are sent.

For LINE messages, you can send text or images and links.

To deliver SMS or LINE messages to a mobile phone you need:

* An external account configured on the **[!UICONTROL Mobile (SMS)]** channel or on the **[!UICONTROL LINE]** channel. 
* An SMS or LINE delivery template that is correctly linked to this external account.

## Push notifications {#push-notifications}

Adobe Campaign allows you to send personalized and segmented [push notifications](push/push.md) on iOS and Android mobile devices, through dedicated apps. Once configuration and integration steps have been performed, iOS and Android deliveries can be created and sent. You can also design rich notifications with images or videos.

## Direct mail {#direct-mail}

[Direct mail](direct/about-direct-mail-channel.md) is an offline channel that allows you to personalize and generate the file required by direct mail providers. It gives you the possibility to mix online and offline channels in your customer journeys.

Online channels allow you to create your messages (email, SMS, mobile app delivery, etc.) and send them to your audience directly from Adobe Campaign. With offline channels, it is different. When you prepare a direct mail delivery, Adobe Campaign generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.

## Other channels {#other-channels}

Adobe Campaign offers Telephone delivery template, which is used to create external deliveries. Using this channel implies you set up dedicated methodologies to process output files. Configuration steps are the same as for [Direct mail channel](direct/about-direct-mail-channel.md).

>[!NOTE]
>
>The Telephone channel is not available out-of-the-box. Its implementation requires Adobe Consulting or an Adobe Partner to be engaged. Please reach out to your Adobe representative for more information.

In addition, 'Other' type deliveries use a specific technical template which does not execute a process: this lets them manage marketing actions executed outside of the Adobe Campaign platform.

This channel has no specific mechanism. It is a generic channel that has its own external account routing option, delivery template type and campaign workflow activity, just like any other communication channel available in Adobe Campaign.

This channel is designed for descriptive purposes only, for example to define deliveries for which you want to keep a trace of the target of a campaign performed in a tool other than Adobe Campaign.

## Types of deliveries{#types-of-deliveries}

There are three types of delivery objects in Campaign:

### Single delivery {#single-delivery}

A **delivery** is a standalone delivery object that is executed once. It can be duplicated, prepared again, but as long as it is in its final state (canceled, stopped, finished), it cannot be reused.

Deliveries can be created either from the list of deliveries, or within a workflow via a [Delivery](../../workflow/using/delivery.md) activity.

Workflows also provide specific delivery activities according to the type of channel you want to use. For more on these activities, refer to [this section](../../workflow/using/cross-channel-deliveries.md).

### Recurring delivery {#recurring-delivery}

A **recurring delivery** lets you create a new delivery each time the activity is executed. This avoids you having to create a new delivery for recurring tasks.

As an example, if you run this type of activity once a month, you will end up with 12 deliveries after a year.

Recurring deliveries are created within workflows via the [Recurring delivery activity](../../workflow/using/recurring-delivery.md). An example of this activity being used is presented in [this section](../../workflow/using/sending-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

### Continuous delivery {#continuous-delivery}

A **continuous delivery** lets you add new recipients to an existing delivery, which avoids having to create a new delivery each time it is executed.

If an information in the delivery changes (content, name, etc.), a new delivery object is created at the delivery execution. If no information was changed, the same delivery object is reused and the delivery and tracking logs are added in the same object.

As an example, if you run this type of activity once a month, you will end up with a single delivery after a year (provided you did not make any change to the delivery).

Continuous deliveries are created within workflows via the [Continuous delivery activity](../../workflow/using/continuous-delivery.md).

## Key steps to create deliveries {#about-delivery-creation}

The key steps when creating a delivery are as follows:

1. **Create and identify the delivery**. [Read more](steps-create-and-identify-the-delivery.md)

1. **Define the delivery content**. [Read more](steps-create-and-identify-the-delivery.md#content)

1. **Define the target population**. [Read more](steps-defining-the-target-population.md)

1. **Send the delivery**. [Read more](steps-sending-the-delivery.md)

1. **Monitor the delivery**: tracking, quarantine, reports, and more. Refer to [Monitoring deliveries](about-delivery-monitoring.md) and [Tracking deliveries](about-message-tracking.md).

