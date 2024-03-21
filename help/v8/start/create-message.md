---
title: Get started with messages
description: Get started with messages
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
---
# Get Started with messages{#gs-ac-audiences}

With Adobe Campaign, you can send cross-channel campaigns including emails, SMS, Push notifications and direct mails, and measure their effectiveness using various dedicated reports. These messages are designed and sent though deliveries, and can be personalized for each recipient.

Core functionalities include targeting, definition and personalization of messages, execution of communications, and the associated operational reports. The main functional access point is the delivery assistant. This access point leads to multiple capabilities covered by Adobe Campaign.

Adobe Campaign v8 comes with the following delivery channels:

* **Email channel**: email deliveries let you send personalized emails to the target population. Learn more in [this page](../send/email.md).

* **Direct mail channel**: direct mail deliveries let you generate an extraction file which contains data on the target population.  Learn more in [this page](../send/direct-mail.md)

* **Mobile channel**: deliveries on mobile channels let you send personalized SMS to the target population.  Learn more in [this page](../send/sms.md)

* **Mobile application channel**: mobile app deliveries let you send notifications to iOS and Android systems.  Learn more in [this page](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Choose how to send your messages{#gs-send-msg}

Once your message has been created and its content designed and tested, you can choose how you want to send it. Campaign offers a set of capabilities to:

* Send messages manually to the main target

    ![](assets/send-email.png) 

   Learn how to send messages in [this section](../send/send.md)

* Send messages associated to a [marketing campaign](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png) 

   Learn how to send messages in the context of a campaign in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html)

* Send messages via a [workflow](../config/workflows.md)

    ![](assets/send-in-a-wf.png) 

   Learn how to automate email deliveries in [this page](../../automation/workflow/delivery.md)

* [Trigger messages](../send/transactional.md) from an event

* Schedule your messages

   ![](assets/schedule-send.png) 
   
   [Use case: learn how schedule and send a birthday email](../../automation/workflow/send-a-birthday-email.md)


## Add personalization{#personalization}

Messages delivered by Adobe Campaign can be personalized in various ways. [Learn more about personalization capabilities](../send/personalize.md)

You can:

* Insert dynamic personalization fields. [Learn more](../send/personalization-fields.md)
* Insert pre-defined personalization blocks. [Learn more](../send/personalization-blocks.md)
* Create conditional content. [Learn more](../send/conditions.md)

## Send transactional messages{#gs-transac-messages}

Transactional messaging (Message Center) is the Campaign module designed for managing trigger messages. 

Learn more about transactional messages capability in [this section](../architecture/architecture.md#transac-msg-archi)

Steps to configure and send transactional messages are detailed in [this page](../send/transactional.md)


## Delivery and tracking logs{#gs-tracking-logs}

Monitoring your deliveries after they have been sent is a key step to ensure your maketing campaigns are efficient and reach out to your customers. You can monitor after sending a delivery, as well as understand how delivery failures and quarantines are managed.

Learn how to monitor your deliveries in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html#sending-messages){target="_blank"}

