---
title: Get started with messages
description: Get started with messages
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
---
# Get Started with messages {#gs-ac-audiences}

## Delivery channels {#gs-ac-channels}

With Adobe Campaign, you can send cross-channel campaigns including emails, SMS, Push notifications and direct mails, and measure their effectiveness using various dedicated reports. These messages are designed and sent though deliveries, and can be personalized for each recipient.

Core functionalities include targeting, definition and personalization of messages, execution of communications, and the associated operational reports. The main functional access point is the delivery assistant. This access point leads to multiple capabilities covered by Adobe Campaign.

Adobe Campaign v8 comes with the following delivery channels:

* **Email channel**: email deliveries let you send personalized emails to the target population. [Learn more](#gs-channel-email)

* **Mobile channels**: deliveries on mobile channels let you send personalized messages on mobile devices to the target population. [Learn more](#gs-channel-sms)

* **Mobile application channel**: mobile app deliveries let you send notifications to iOS and Android devices. [Learn more](#gs-channel-push)

* **Direct mail channel**: direct mail deliveries let you generate an extraction file which contains data on the target population. [Learn more](#gs-channel-direct)


   Other channels are described on [this section](#other-channels).

   >[!NOTE]
   >
   >The number of available channels depends on your contract. Please check your license agreement.

## Choose your channel {#gs-channel}

### Email channel {#gs-channel-email}

The [Email channel](../send/direct-mail.md) is one of the core channels in Adobe Campaign, allowing you to schedule and send personalized emails to specific targets.

You can send different types of emails:

* Single-send emails: emails that you can send once to a defined target. They are usually used to promote a specific content that would be prepared and sent only once (newsletter, promotional email, etc.).
* Recurring emails: in a campaign, send the same email regularly and aggregate each send and its reports on a periodic basis. The same email is sent, but usually to a different target, based on the eligible target for the day of the send. A common example is a birthday email. For more on this, refer to [Recurring deliveries](../../automation/workflow/recurring-delivery.md).
* Transactional emails: unitary emails that are triggered based on your customers' behavior. Refer to [Transactional messaging](../send/transactional.md).

To learn about delivery usage and recommendations, consult Adobe Campaign Classic [Delivery best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"}

For more on the different types of deliveries, refer to [this section](#types-of-deliveries).

### Mobile channel {#gs-channel-sms}

Adobe Campaign allows you to deliver [SMS](../send/sms.md) and [LINE](../send/line.md) messages on mobiles.

For SMS messages, you can create, modify, and personalize messages in text format only. You can also preview your SMS messages before they are sent.

For LINE messages, you can send text or images and links.

To deliver SMS or LINE messages to a mobile phone you need:

* An external account configured on the **[!UICONTROL Mobile (SMS)]** channel or on the **[!UICONTROL LINE]** channel. 
* An SMS or LINE delivery template that is correctly linked to this external account.


### Push notification channel {#gs-channel-push}

You can use Adobe Campaign to send personalized and segmented [push notifications](../send/push.md) on iOS and Android mobile devices, through dedicated apps. Once configuration and integration steps have been performed, iOS and Android deliveries can be created and sent with Adobe Campaign. You can also design and send rich notifications with images or videos to Android devices.

### Direct mail channel {#gs-channel-direct}

[Direct mail](../send/direct-mail.md) is an offline channel that allows you to create, personalize and generate an external file to share with your direct mail providers. Use this channel to orchestrate online and offline channels in your customer journeys.

When you prepare a direct mail delivery, Adobe Campaign generates a file including all the targeted profiles and the chosen contact information (postal address for example). You can then send this file to your direct mail provider who will take care of the actual sending.


### Other channels {#other-channels}

Adobe Campaign also comes with a Telephone delivery template, which is used to create external deliveries. Using this channel implies you implement dedicated methodologies to process output files. Configuration steps are the same as for [Direct mail channel](../send/direct-mail.md).

>[!NOTE]
>
>The Telephone channel is not a built-in channel. Its implementation requires Adobe Consulting or an Adobe Partner to be engaged. Please reach out to your Adobe representative for more information.

The 'Other' type deliveries use a specific technical template which does not execute a process: this lets them manage marketing actions executed outside of the Adobe Campaign platform.

This channel has no specific mechanism. It is a generic channel that has its own external account routing option, delivery template type, and campaign workflow activity, just like any other communication channel available in Adobe Campaign. This channel is designed for descriptive purposes only, for example to define deliveries for which you want to keep a trace of the target of a campaign performed in a tool other than Adobe Campaign.

## Choose the type of delivery {#types-of-deliveries}

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


## Choose how to send your messages{#gs-send-msg}

Once your message has been created and its content designed and tested, you can choose how you want to send it. Campaign offers a set of capabilities to:

* Send messages manually to the main target

    ![](assets/send-email.png) 

   Learn how to send messages in [this section](../send/send.md)

* Send messages associated to a [marketing campaign](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png) 

   Learn how to send messages in the context of a campaign in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html){target="_blank"}

* Send messages via a [workflow](../config/workflows.md)

    ![](assets/send-in-a-wf.png) 

   Learn how to automate email deliveries in [this page](../../automation/workflow/delivery.md)

* [Trigger messages](../send/transactional.md) from an event

   Transactional messaging (Message Center) is the Campaign module designed for managing trigger messages. 

   Learn more about transactional messages capability in [this section](../architecture/architecture.md#transac-msg-archi)

   Steps to configure and send transactional messages are detailed in [this page](../send/transactional.md)

* Schedule your messages

   ![](assets/schedule-send.png) 
   
   Learn how to schedule the sending of your deliveries in [this page](../send/configure-and-send.md)

   See also this [Use Case: learn how schedule and send a birthday email](../../automation/workflow/send-a-birthday-email.md)


## Add personalization{#personalization}

Messages delivered by Adobe Campaign can be personalized in various ways. [Learn more about personalization capabilities](../send/personalize.md)

You can:

* Insert dynamic personalization fields. [Learn more](../send/personalization-fields.md)
* Insert pre-defined personalization blocks. [Learn more](../send/personalization-blocks.md)
* Create conditional content. [Learn more](../send/conditions.md)


## Delivery and tracking logs{#gs-tracking-logs}

Monitoring your deliveries after they have been sent is a key step to ensure your maketing campaigns are efficient and reach out to your customers. You can monitor after sending a delivery, as well as understand how delivery failures and quarantines are managed.

Learn how to monitor your deliveries in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"}

