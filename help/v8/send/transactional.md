---
title: Campaign Transactional messaging
description: Get started with Transactional messaging
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
---
# Get Started with Transactional messaging{#send-transactional-messages}

Transactional messaging (Message Center) is a Campaign module designed for managing trigger messages. These notifications are generated from events triggered from information systems, and can be: invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement, website account creation, etc.

>[!NOTE]
>
>As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} to configure Campaign Transactional messaging in your environment.

Transactional messages are used to send:

* notifications, such as order confirmations or password resets for example
* an individual real-time response to a customer action
* non-promotional content

Transactional messaging settings are detailed in [this section](../config/transactional-msg-settings.md).

Understand transactional messaging architecture on [this page](../architecture/architecture.md#transac-msg-archi).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

The Adobe Campaign Transactional messaging module integrates into an information system which returns events to be changed into personalized transactional messages. These messages can be sent individually or in batches via email, SMS or push notifications.

For example, imagine you are a company with a website where your customers can buy products.

Adobe Campaign allows you to send a notification email to customers who have added products to their cart. When one of them leaves your website without going through with their purchases (external event which triggers a Campaign event), a cart abandonment email is automatically sent to them (transactional message delivery).

The main steps for putting this into place are detailed below:

1. [Create an event type](#create-event-types).
1. [Create and design the message template](transactional-template.md#create-message-template). You must link an event to your message during this step.
1. [Test the message](transactional-template.md#test-message-template).
1. [Publish the message template](transactional-template.md#publish-message-template).

Once you designed and published the transactional message template, if a corresponding event is triggered, the relevant data are sent to Campaign via the PushEvent and PushEvents [SOAP methods](../send/event-description.md), and the delivery is sent to the targeted recipients.

## Create event types {#create-event-types}

To make sure each event can be changed into a personalized message, you first need to create **event types**.

When [creating a message template](#create-message-template), you will select the type of event that matches the message you want to send.

>[!CAUTION]
>
>You must create event types before being able to use them in message templates.

To create event types that will be processed by Adobe Campaign, follow the steps below:

1. Browse to the **[!UICONTROL Administration > Platform > Enumerations]** folder of Campaign explorer.
1. Select the **[!UICONTROL Event type]** enumeration from the list.
1. Click **[!UICONTROL Add]** to create an enumeration value. This can be an order confirmation, password change, order delivery change, etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Each event type must match a value in the **[!UICONTROL Event type]** enumeration.

1. Once the itemized list values have been created, log off and back on to your instance for the creation to be effective.

>[!NOTE]
>
>Learn more about enumerations in [this page](../../v8/config/ui-settings.md#enumerations).

For next step, learn how to [create and publish your template for Transactional messaging](transactional-template.md).
