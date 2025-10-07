---
title: Get started with messages
description: Get started with messages
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a523e76d-776c-47d3-9c15-34241cee1092
---
# Get Started with messages {#gs-ac-msg}

With Adobe Campaign, you can send cross-channel campaigns including emails, SMS, Push notifications and direct mails, and measure their effectiveness using various dedicated reports. These messages are designed and sent though deliveries, and can be personalized for each recipient.

Core functionalities include targeting, definition and personalization of messages, execution of communications, and the associated operational reports.

## Use cases {#gs-ac-delivery}

To send messages, you must create a delivery. The delivery creation mode depends on your use case.

>[!NOTE]
>
>When creating a delivery, you must select a template. Default templates are available for each channel. Learn more about delivery templates in [this page](../send/create-templates.md).

1. **One-shot messages** - You can send one-shot messages to an audience. Learn how to send your first message in [this section](create-message.md).

    ![](assets/send-email.png)

1. **Messages in a marketing campaign** - You can send messages in the context of a [marketing campaign](campaigns.md), define an approval process, send and track them in a consolidated dashboard. Learn how in [this section](../../automation/campaigns/marketing-campaign-deliveries.md).

    ![](assets/deliveries-in-a-campaign.png) 

1. **Messages in a workflow** - You can send messages via a [workflow](../config/workflows.md) and automate your deliveries. Learn how in [this page](../../automation/workflow/delivery.md).

    ![](assets/send-in-a-wf.png) 

1. **Triggered messages** - You can [Trigger messages](../send/transactional.md) from an event. Transactional messaging (Message Center) is the Campaign module designed for managing trigger messages. Steps to configure and send transactional messages are detailed in [this page](../send/transactional.md)

## Communication channels {#gs-channel}

Adobe Campaign v8 comes with the delivery channels listed below. The channels available in your environment depends on your contract. Please check your license agreement.

* **Email channel**: email deliveries let you send personalized emails to the target population. [Learn more](../send/email.md)

* **Mobile channels**: deliveries on mobile channels let you send personalized messages on mobile devices to the target population. You can send [SMS](../send/sms/sms.md) and [LINE](../send/line/line.md) messages on mobiles.

* **Mobile application channel**: You can use Adobe Campaign to send personalized and segmented [push notifications](../send/push.md) on iOS and Android mobile devices, through dedicated apps. Once configuration and integration steps have been performed, iOS and Android deliveries can be created and sent with Adobe Campaign. You can also design and send rich notifications with images or videos to Android devices.

* **Direct mail channel**: [Direct mail](../send/direct-mail.md) is an offline channel that allows you to create, personalize and generate an external file to share with your direct mail providers. Use this channel to orchestrate online and offline channels in your customer journeys.

    When you prepare a direct mail delivery, Adobe Campaign generates a file including all the targeted profiles and the chosen contact information (postal address for example). You can then send this file to your direct mail provider who will take care of the actual sending.


* **Other channels**: Adobe Campaign also comes with a Telephone delivery template, which is used to create external deliveries. Using this channel implies you implement dedicated methodologies to process output files. Configuration steps are the same as for [Direct mail channel](../send/direct-mail.md).

    >[!NOTE]
    >
    >The Telephone channel is not a built-in channel. Its implementation requires Adobe Consulting or an Adobe Partner to be engaged. Please reach out to your Adobe representative for more information.

    The 'Other' type deliveries use a specific technical template which does not execute a process: this lets them manage marketing actions executed outside of the Adobe Campaign platform.

    This channel has no specific mechanism. It is a generic channel that has its own external account routing option, delivery template type, and campaign workflow activity, just like any other communication channel available in Adobe Campaign. This channel is designed for descriptive purposes only, for example to define deliveries for which you want to keep a trace of the target of a campaign performed in a tool other than Adobe Campaign.

## Types of delivery {#types-of-deliveries}

There are three types of delivery objects in Campaign:

### Single delivery {#single-delivery}

A **delivery** is a standalone delivery object that is executed once. It can be duplicated, prepared again, but as long as it is in its final state (canceled, stopped, finished), it cannot be reused.

Deliveries can be created either from the list of deliveries, or within a workflow via a [Delivery](../../automation/workflow/delivery.md) activity. 

Workflows also provide specific delivery activities according to the type of channel you want to use. For more on these activities, refer to [this section](../../automation/workflow/cross-channel-deliveries.md).

### Recurring delivery {#recurring-delivery}

A **recurring delivery** is available in the context of a workflow. It lets you create a new delivery each time the activity is executed. This avoids you having to create a new delivery for recurring tasks. As an example, if you run this type of activity once a month, you will end up with 12 deliveries after a year.

Recurring deliveries are created within workflows via the [Recurring delivery activity](../../automation/workflow/recurring-delivery.md). An example of this activity being used is presented in this section: [Creating a recurring delivery in a targeting workflow](../../automation/workflow/send-a-birthday-email.md).

### Continuous delivery {#continuous-delivery}

A **continuous delivery** is available in the context of a workflow. It lets you add new recipients to an existing delivery, which avoids having to create a new delivery each time it is executed.

If an information in the delivery changes (content, name, etc.), a new delivery object is created at the delivery execution. If no information was changed, the same delivery object is reused and the delivery and tracking logs are added in the same object.

As an example, if you run this type of activity once a month, you will end up with a single delivery after a year (provided you did not make any change to the delivery).

Continuous deliveries are created within workflows via the [Continuous delivery activity](../../automation/workflow/continuous-delivery.md).

## Personalization capabilities {#personalization}

Messages delivered by Adobe Campaign can be personalized in various ways. [Learn more about personalization capabilities](../send/personalize.md)

You can:

* Insert dynamic personalization fields. [Learn more](../send/personalization-fields.md)
* Insert pre-defined personalization blocks. [Learn more](../send/personalization-blocks.md)
* Create conditional content. [Learn more](../send/conditions.md)


## Tracking and monitoring {#gs-tracking-logs}

Monitoring your deliveries after they have been sent is a key step to ensure your maketing campaigns are efficient and reach out to your customers. You can monitor after sending a delivery, as well as understand how delivery failures and quarantines are managed.

Learn how to monitor your deliveries in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"}
