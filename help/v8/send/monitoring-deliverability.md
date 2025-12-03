---
product: campaign
title: Monitor deliverability in Adobe Campaign
description: Learn about tools and guidelines on deliverability monitoring in Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
---
# Monitor your deliverability{#monitoring-deliverability}

Below you will find details on the different monitoring tools provided by Adobe Campaign, as well as some additional guidelines on leveraging the features offered by Adobe Campaign to monitor your platform's deliverability.

## Monitoring tools {#monitoring-tools}

Adobe Campaign gives you access to the deliverability tools listed below.

### Inbox rendering {#inbox-rendering-tool}

The [Inbox rendering report](inbox-rendering.md) enables you to preview your messages on major email clients in order to scan content and reputation.

### Delivery throughput {#throughput-reports}

The **[!UICONTROL Delivery throughput]** report gives you an overview of the entire platform's throughput for a given period. For more on this, see [this section](../reporting/global-reports.md#delivery-throughput).

### Broadcast statistics {#broadcast-statistics}

Each delivery generates a broadcast statistics report for the different Internet service providers (ISPs). It shows some data quality and reputation metrics that may impact your deliverability, including the following numbers:

**[!UICONTROL Hard bounces]** indicate data quality. This number should be less than 2%.

**[!UICONTROL Soft bounces]** indicate reputation. This number should not be higher than 10% for any given ISP.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Delivery dashboard {#delivery-dashboard-monitoring}

More generally, the [delivery dashboard](delivery-dashboard.md) gives you access to:

The delivery summary, which shows the detail of the sending and the number of messages to send, processed and sent with success.

The delivery logs and history, which show which target has been excluded and why.

The tracking logs, which show tracking information such as opens and clicks.

### SpamAssassin testing {#spam-testing}

Use [SpamAssassin](spamassassin.md) to test your email content and score it to determine whether a message runs the risk of being considered as spam by the anti-spam tools used upon receipt.

### Control Panel {#control-panel-monitoring}

>[!NOTE]
>
>Control Panel is available for Campaign v8 Managed Cloud Services users. Learn more about [Control Panel](../config/self-service.md).

Campaign [Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html){target="_blank"} provides monitoring capabilities for deliverability, including subdomain and certificate management, active profiles monitoring, and delivery throughput and latency metrics.

## Monitoring guidelines {#monitoring-guidelines}

Here are some additional guidelines on deliverability monitoring:

### Platform throughput monitoring

Regularly check the [delivery throughput](../reporting/global-reports.md#delivery-throughput) for the whole platform to verify whether it is consistent with the original set-up.

### Retry configuration

Check that [retries](delivery-failures.md#retries) are set up correctly (30 minutes for retry period and more than 20 retries) in delivery templates.

### Bounce mailbox verification

Regularly verify that the [bounce](delivery-failures.md#bounce-mail-qualification) mailbox is accessible and that the account is not about to expire.

### Delivery performance checks

Check each delivery throughput, accessible from the [delivery dashboard](delivery-dashboard.md), to make sure that it is consistent with the delivery content's validity (e.g. 'flash sales' should be delivered in minutes, not days).

### Wave timing validation

When using [waves](configure-and-send.md#sending-using-multiple-waves), verify that each wave has enough time to finish before the next one is triggered.

### Quarantine monitoring

Check that the number of errors and new [quarantines](quarantines.md) are consistent with other deliveries.

### Delivery log analysis

Carefully consult the [delivery logs](delivery-dashboard.md#delivery-logs-and-history) in detail to check the kind of errors that are highlighted (denylists, DNS issues, anti-spam rules, etc.).

## Related topics

[Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"} provides comprehensive guidance on deliverability strategy, definition, metrics, and best practices.

[What is deliverability](about-deliverability.md) introduces key deliverability concepts and how to improve your deliverability rate in Campaign.

[Delivery failures and bounces](delivery-failures.md) describes the different types of delivery failures, how Campaign handles them, and includes troubleshooting guidance for common issues.

[Quarantine management](quarantines.md) explains how Campaign manages quarantined addresses to protect your sending reputation.

[Control message content](control-message-content.md) provides guidance on how to ensure your content is optimized for deliverability.
