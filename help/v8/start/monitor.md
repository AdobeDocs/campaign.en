---
title: Monitor your Campaign environment
description: Learn how to monitor deliveries, workflows, and your Campaign instance
feature: Monitoring
role: User
level: Beginner
exl-id: a5c9a84e-4f39-4f3c-8a8e-3d1e5e5e5e5e
---
# Monitor your Campaign environment {#monitor-campaign}

Adobe Campaign offers a comprehensive set of capabilities to monitor your processes, deliveries, and environment to ensure optimal performance and troubleshoot issues proactively.

>[!NOTE]
>
>As a Campaign administrator, you can also use [Campaign Control Panel](#control-panel) to monitor your instances, manage performance, and configure settings with self-service capabilities.

## Monitor your deliveries {#monitor-deliveries}

Monitoring your deliveries after they have been sent is a key step to ensure your marketing campaigns are efficient and reach out to your customers.

### Email delivery monitoring {#email-monitoring}

After sending an email delivery, you can monitor its status and track key metrics in the delivery dashboard.

The delivery dashboard provides:

* **Delivery logs**: View which recipients successfully received the email
* **Exclusion logs**: Understand why certain recipients were excluded from the delivery
* **Tracking logs**: Monitor opens, clicks, and other recipient interactions with your email content

Learn more about [email delivery monitoring](../send/send.md#email-monitoring)

### SMS delivery monitoring {#sms-monitoring}

For SMS deliveries, you can track the delivery status and monitor key metrics such as:

* Messages sent and delivered
* Delivery failures and bounces
* Recipient interactions with SMS content

Learn more about [SMS monitoring](../send/sms/sms-monitor.md)

### Push notification monitoring {#push-monitoring}

Monitor your push notification deliveries to ensure they reach your mobile app users effectively.

Learn more about [push notification monitoring](../send/push.md#push-test)

### Transactional message monitoring {#transactional-monitoring}

For transactional messages triggered by events, you can monitor:

* Event processing status
* Message execution and delivery status
* Processing errors and failed events

Learn more about [transactional message monitoring](../send/delivery-execution.md#monitor-transactional-msg)

### Understand delivery failures {#delivery-failures}

Understanding why a delivery failed is critical to maintain a clean database and ensure good deliverability rates.

Adobe Campaign classifies delivery failures into three types:

* **Hard bounces**: Permanent failures (invalid email address, domain doesn't exist)
* **Soft bounces**: Temporary failures (mailbox full, server temporarily unavailable)
* **Ignored**: Delivery ignored by Adobe Campaign (unsubscribed, quarantine)

Learn more about [delivery failures and quarantines](../send/delivery-failures.md)

## Monitor deliverability {#monitor-deliverability}

Deliverability monitoring helps you ensure that your messages reach your recipients' inboxes and avoid spam filters.

### Deliverability monitoring tools {#deliverability-tools}

Adobe Campaign provides several built-in tools to monitor and improve deliverability:

* **Delivery reports**: Track opens, clicks, bounces, and spam complaints
* **Inbox rendering**: Preview how your email displays across different email clients and devices
* **SpamAssassin**: Test your email content for spam triggers before sending
* **Feedback loops**: Receive notifications when recipients mark your messages as spam

Learn more about [deliverability monitoring](../send/monitoring-deliverability.md)

### Deliverability best practices {#deliverability-best-practices}

Follow these key practices to maintain good deliverability:

* Maintain a clean email list with regular bounce and unsubscribe processing
* Use double opt-in for new subscribers
* Monitor your sender reputation and IP address reputation
* Warm up new IP addresses gradually
* Authenticate your sending domains with SPF, DKIM, and DMARC

Learn more about [deliverability best practices](../send/about-deliverability.md)

## Monitor workflows {#monitor-workflows}

Workflows are essential to automate your marketing campaigns and data processing. Monitoring workflow execution helps you:

* Ensure workflows complete successfully
* Identify and troubleshoot errors
* Optimize workflow performance

### Workflow monitoring capabilities {#workflow-monitoring}

You can monitor:

* **Workflow execution status**: Running, paused, failed, or completed
* **Activity execution logs**: Detailed logs for each workflow activity
* **Workflow heatmap**: Visualize workflow execution patterns and identify bottlenecks
* **Workflow history**: Track all workflow executions and modifications

Learn more about [workflow monitoring](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

## Monitor your instance {#monitor-instance}

Instance monitoring helps you ensure the health and performance of your Adobe Campaign environment.

### Audit trail {#audit-trail}

The Audit trail self-service interface allows you to monitor changes made within your Adobe Campaign instance. Audit trail captures, in real-time, a comprehensive list of actions and events occurring within your instance.

Use Audit trail to:

* Track what happened to your workflows, schemas, options, and other components
* Identify who last updated a specific element
* Understand what users did in the instance
* Maintain compliance and security by tracking all configuration changes

Learn more about [Audit trail](../reporting/audit-trail.md)

### Performance monitoring {#performance-monitoring}

Monitor the performance of your Campaign instance to ensure optimal operation:

* **Database performance**: Track query execution times and database load
* **Server resources**: Monitor CPU, memory, and disk usage
* **Campaign processes**: Ensure all technical workflows are running correctly
* **Delivery throughput**: Monitor the number of messages sent per hour

### Technical workflows {#technical-workflows}

Technical workflows are essential processes that run in the background to maintain your Campaign instance. Regularly monitor technical workflows to ensure they are:

* Executing on schedule
* Completing successfully without errors
* Processing data correctly

Key technical workflows to monitor include:

* **Tracking workflow**: Processes tracking data from email deliveries
* **Cleanup workflow**: Removes old data and logs to maintain database performance
* **Deliverability update**: Updates deliverability rules and spam filter patterns
* **Database cleanup**: Purges old delivery and tracking logs

### Campaign Control Panel {#control-panel}

Campaign Control Panel provides administrators with self-service capabilities to monitor and manage Campaign instances.

**Performance monitoring**

Control Panel offers several functionalities to monitor your instances and ensure optimal performance:

* **Active profiles monitoring**: Track active profile usage against your contractual limits
* **Database monitoring**: Monitor database usage, storage capacity, and performance
* **Workflow monitoring**: View workflow execution status and identify long-running workflows
* **Throughput and latency**: Monitor delivery throughput and system latency

**Infrastructure monitoring**

* **SFTP storage monitoring**: Monitor SFTP server storage capacity and usage
* **Subdomain monitoring**: Track subdomain configuration and delegation status
* **SSL certificate monitoring**: Monitor SSL certificate expiration dates and renewal status
* **IP allow listing**: Manage and monitor IP addresses authorized to access your instance

**Instance settings and details**

* **Instance details**: View key information about your Campaign instances including build version, installed packages, and system configuration
* **URL permissions**: Monitor and manage authorized external domains for your instance

Learn more about [Control Panel](../config/self-service.md) and [Control Panel performance monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html){target="_blank"}

### Instance monitoring guidelines {#instance-guidelines}

For comprehensive instance monitoring guidelines, including server configuration, database maintenance, and log analysis, refer to [Campaign Classic v7 monitoring documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html){target="_blank"}

## Tracking and reporting {#tracking-reporting}

### Message tracking {#message-tracking}

Track recipient behavior and measure the effectiveness of your campaigns:

* **Opens**: Track when recipients open your emails
* **Clicks**: Monitor which links recipients click
* **Unsubscribes**: Track opt-out requests
* **Mirror page views**: See how many recipients view your email in a browser

Learn more about [message tracking](../send/tracking.md)

### Delivery reports {#delivery-reports}

Adobe Campaign provides a comprehensive set of reports to analyze your delivery performance:

* **Delivery summary**: Overview of sends, deliveries, and failures
* **Tracking indicators**: Opens, clicks, and click-through rates
* **URLs and click streams**: Most popular links in your deliveries
* **Hot clicks**: Visual representation of where recipients clicked in your email

Learn more about [delivery reports](../reporting/delivery-reports.md)

### Global reports {#global-reports}

Access global reports to analyze performance across all campaigns and deliveries:

* **Delivery throughput**: Messages sent over time
* **Non-deliverables and bounces**: Analysis of failed deliveries
* **User activities**: Opens, clicks, and unsubscribes across all campaigns

Learn more about [global reports](../reporting/global-reports.md)

## Related topics {#related-topics}

* [Get started with message tracking](../send/tracking.md)
* [Delivery best practices](delivery-best-practices.md)
* [Control message content](../send/control-message-content.md)

