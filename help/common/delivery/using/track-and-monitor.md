---
product: campaign
title: Track and monitor messages
description: Delivery best practices 
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
exl-id: a039a288-2e7b-4f35-9885-ead3ed4347af
---
# Track and monitor {#track-and-monitor}

![](assets/do-not-localize/common.svg)

You clicked the **Send** button? Let's see what happens. Once the delivery is sent, Adobe Campaign enables you to keep track of the sent messages and discover how your recipients react to your delivery. This will help you improve future sending and optimize your next campaigns.

## Monitoring deliveries {#monitoring-deliveries}

To control your campaigns, you must ensure that the message has indeed been delivered to your recipients.

From Campaign delivery dashboard, you can check the processed messages and delivery audit logs.
You can also control the status of the messages in the delivery logs. [Learn more](about-delivery-monitoring.md).

What if the deliveries are not being sent and their status remains **Pending**?

* The execution process is waiting on the availability of some resources. The MTA may have not been started.
Check that your mta@instance modules are launched on your MTA servers and start the MTA module if necessary. [Learn more in Campaign Classic v7 documentation](../../../v7/production/using/administration.md).

* The delivery may be using an affinity that has not been configured on the sending instance.
Tip: Check the configuration of traffic management (IP affinity). For more on this, see Control outgoing SMTP traffic.

>[!NOTE]
>
>These steps can only be performed by an expert user.

## Tracking {#tracking-deliveries}

To better know the behavior of your recipients, you can track how they react to a delivery: reception, opening, clicks on links, unsubscriptions, etc. In Campaign Classic, this information is displayed in the Tracking tab of the recipients targeted by the delivery and in the Tracking tab of the delivery.

**Tip**: Message tracking is enabled by default. To configure URLs, select the Display URLs option in the lower section of the delivery wizard. For each URL of the message, you can choose whether to activate tracking.

For more on this, refer to the [Configuring tracking](how-to-configure-tracked-links.md) section and the [Tracking indicators](../../reporting/using/delivery-reports.md#tracking-indicators) description. 

## Delivery performances {#delivery-performances}

To measure the speed at which the messages are delivered, you can control the delivery throughput. The criteria are the number of messages sent per hour and the size of the messages (in bits per second). For more on this, see [Delivery throughput](../../reporting/using/global-reports.md#delivery-throughput).

**Tips**:

* Do not keep deliveries in failed state on the instance, as this maintains temporary tables and impacts the performance.

* Remove deliveries which are no longer needed and inactive recipients from the database to maintain address quality.

* Do no try to schedule large deliveries together. Please note that it can take 5 to 10 minutes to spread the load uniformly over the system.

## Delivery troubleshooting {#delivery-troubleshooting}

You can take actions when facing issues with deliveries. Learn more in the following pages:

* [Delivery performance issues](delivery-performances.md)

* [Temporary files issues](../../../v7/production/using/temporary-files.md) in Campaign Classic v7 - *on-premise customers only*

* [Deliverability issues](../../../v7/production/using/performance-and-throughput-issues.md#deliverability_issues) in Campaign Classic v7 

* [Image display issues](../../../v7/production/using/image-display-issues.md) in Campaign Classic v7 
