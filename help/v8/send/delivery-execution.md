---
title: Transactional messages delivery execution
description: Learn more about transactional messages delivery execution and monitoring
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
---

# Delivery execution {#delivery-execution}

Once the enrichment is complete and a delivery template has been linked to the event, the delivery is sent from the execution instance.

>[!NOTE]
>
>The transactional messages are prioritized over any other delivery.

All deliveries are grouped in the **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** folder.

By default, they are sorted into sub-folders by delivery month. This sort can be changed in the message template properties.

## Transactional message monitoring {#transactional-message-monitoring}

To monitor your transactional messages, check the [delivery logs](send.md).

The transactional deliveries sent from the execution instance are synchronized back to the control instance through a technical workflow (**[!UICONTROL Message Center execution instance]**) that runs every hour.
 
>[!NOTE]
>
>The deliveries weekly accumulate the events based on the latest event update, and not on the event creation date. Therefore, when extracting transactional messaging delivery logs from the control instance, the delivery ID associated with each delivery log ID may change over time as the log is updated (for example, when an inbound bounce is received for the event).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
