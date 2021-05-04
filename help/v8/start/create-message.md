---
solution: Campaign Classic
product: campaign
title: Get started with messages
description: Get started with messages
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
---
# Get Started with messages{#gs-ac-audiences}

With Adobe Campaign, you can send cross-channel campaigns including emails, SMS, LINE messages, Push notifications and direct mails, and measure their effectiveness using various dedicated reports. These messages are designed and sent though deliveries, and can be personalized for each recipient.

Core functionalities include targeting, definition and personalization of messages, execution of communications, and the associated operational reports. The main functional access point is the delivery assistant. This access point leads to multiple capabilities covered by Adobe Campaign.

Learn key steps to create a delivery in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 comes with the following delivery channels:

* **Email channel**: email deliveries let you send personalized emails to the target population. Learn more in [this page](../send/email.md).

* **Direct mail channel**: direct mail deliveries let you generate an extraction file which contains data on the target population.  Learn more in [this page](../send/direct-mail.md)

* **Mobile channel**: deliveries on mobile channels let you send personalized SMS to the target population.  Learn more in [this page](../send/sms.md)

* **Mobile application channel**: mobile app deliveries let you send notifications to iOS and Android systems.  Learn more in [this page](../send/push.md)

## Choose how to send your messages 

Once your message has been created and its content designed and tested, you can choose how you want to send it. Campaign offers a set of capabilities to:

* Send messages manually to the main target
    :arrow_upper_right: [Learn how to send messages](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Send messages associated to a [marketing campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)
    :arrow_upper_right: [Learn how to send messages in the context of a campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Send messages via a [workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
    :arrow_upper_right: [Learn how to automate email deliveries](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Trigger messages](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) from an event
    :arrow_upper_right: [Use case: learn how to send a transactional email with an attachment](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Schedule your messages
    :arrow_upper_right: [Use case: learn how schedule and send a birthday email](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Add personalization

Messages delivered by Adobe Campaign can be personalized in various ways. 

You can:

* Insert dynamic personalization fields. 
    :arrow_upper_right: Learn how to use personalization fields in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* Insert predefined personalization blocks. 
    :arrow_upper_right: Learn what is a personalization block and how to use it in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* Create conditional content. 
    :arrow_upper_right: Learn how to insert conditional content in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## Send transactional messages

Transactional messaging (Message Center) is the Campaign module designed for managing trigger messages. 

:bulb: Learn more about transactional messages capability in [this section](../dev/architecture.md#transac-msg-archi)

:bulb: Steps to configure and send transactional messages are detailed in [this page](../send/transactional.md)

:arrow_upper_right: Discover this capability in a end-to-end use case in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Delivery and tracking logs

Monitoring your deliveries after they have been sent is a key step to ensure your maketing campaigns are efficient and reach out to your customers. You can monitor after sending a delivery, as well as understand how delivery failures and quarantines are managed.

:arrow_upper_right: [Learn how to monitor your deliveries in this section](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Related topics**

:arrow_upper_right:  [Delivery best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right:  [Test and send an email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right:  [Send proofs](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
