---
title: Campaign monitoring overview
description: Learn how to monitor deliveries, workflows, and your Campaign instance
feature: Monitoring
role: User
level: Beginner
---
# Campaign monitoring overview {#monitor-campaign}

Adobe Campaign offers a comprehensive set of capabilities to monitor your processes, deliveries, and environment to ensure optimal performance and troubleshoot issues proactively.

>[!NOTE]
>
>As a Campaign administrator, you can also use [Campaign Control Panel](#control-panel) to monitor your instances, manage performance, and configure settings with self-service capabilities.

## Monitor your deliveries {#monitor-deliveries}

Monitoring your deliveries after they have been sent is a key step to ensure your marketing campaigns are efficient and reach out to your customers. After sending a delivery, you can monitor its status and track key metrics in the delivery dashboard. The dashboard provides access to delivery logs, exclusion logs, tracking logs, and other monitoring capabilities to help you analyze your delivery performance across all channels.

**Email deliveries** - Monitor email delivery status, track key metrics, and access detailed logs. Learn more about [monitoring deliveries in Campaign UI](../send/delivery-dashboard.md), [delivery statuses](../send/delivery-statuses.md) and [email delivery monitoring](../send/send.md#email-monitoring).

**SMS deliveries** - Track SMS delivery status and monitor key metrics in the SMS delivery dashboard. Learn more about [SMS monitoring](../send/sms/sms-monitor.md).

**Push notifications** - Monitor push notification deliveries to ensure they reach your mobile app users effectively. Learn more about [push notification monitoring](../send/push.md#push-test).

**Transactional messages** - For messages triggered by events, monitor event processing status, message execution and delivery status. Learn more about [transactional message monitoring](../send/delivery-execution.md#monitor-messages).

**Delivery failures** - Understanding why a delivery failed is critical to maintain a clean database and ensure good deliverability rates. Delivery failures are classified into hard bounces, soft bounces, and ignored messages. Learn more about [delivery failures and quarantines](../send/delivery-failures.md).

## Monitor deliverability {#monitor-deliverability}

Deliverability monitoring helps you ensure that your messages reach your recipients' inboxes and avoid spam filters. Adobe Campaign provides several built-in tools to monitor and improve deliverability, including delivery reports, inbox rendering, SpamAssassin testing, and broadcast statistics. Following deliverability best practices such as maintaining a clean email list, monitoring sender reputation, and authenticating sending domains is critical to maintain good deliverability rates.

Learn more about [deliverability monitoring tools](../send/monitoring-deliverability.md) and [deliverability best practices](../send/about-deliverability.md).

## Monitor workflows {#monitor-workflows}

Workflows are essential to automate your marketing campaigns and data processing. Monitoring workflow execution helps you:

* Ensure workflows complete successfully
* Identify and troubleshoot errors
* Optimize workflow performance

### Workflow monitoring capabilities {#workflow-monitoring}

**Monitor the following workflow elements:**

**Workflow execution status** - Track whether workflows are running, paused, failed, or completed. [Learn more about workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**Activity execution logs** - Access detailed logs for each workflow activity to troubleshoot issues and optimize performance.

**Workflow heatmap** - Visualize workflow execution patterns, identify bottlenecks, and monitor concurrent workflows. The Workflow HeatMap is available to Campaign administrators. [Learn more about workflow heatmap](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html){target="_blank"}

**Workflow history** - Track all workflow executions and modifications over time to understand workflow behavior and performance.

## Monitor your instance {#monitor-instance}

Instance monitoring helps you ensure the health and performance of your Adobe Campaign environment.

### Audit trail {#audit-trail}

The Audit trail self-service interface allows you to monitor changes made within your Adobe Campaign instance. Audit trail captures, in real-time, a comprehensive list of actions and events occurring within your instance.

**Use Audit trail to:**

* **Track component changes**: Monitor what happened to your workflows, schemas, options, and other components
* **Identify who made changes**: See who last updated a specific element and when
* **Understand user actions**: Review what users did in the instance for troubleshooting or auditing
* **Maintain compliance**: Track all configuration changes for compliance and security purposes

The Audit trail is accessible through the Campaign client console and provides detailed information about actions performed by users.

Learn more about [Audit trail](../reporting/audit-trail.md)

### Performance monitoring {#performance-monitoring}

Campaign v8 provides several monitoring capabilities to track your instance performance and ensure optimal operation:

**Database monitoring** - Monitor database usage and capacity through Control Panel to ensure optimal performance and storage management. [Learn more about database monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Active profiles monitoring** - Track active profile usage against your contractual limits to maintain compliance and optimize resource allocation. [Learn more about active profiles](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**Workflow monitoring** - Monitor workflow execution status to identify long-running workflows and ensure all technical workflows are running correctly. [Learn more about technical workflows](#technical-workflows)

**Delivery throughput and latency** - Track delivery throughput (messages sent per hour) and latency for transactional communications through Control Panel. [Learn more about throughput monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, server infrastructure (CPU, memory, disk) is monitored and managed by Adobe.

### Technical workflows {#technical-workflows}

Technical workflows are essential processes that run in the background to maintain your Campaign instance.

**Monitor that technical workflows are:**

* Executing on schedule
* Completing successfully without errors
* Processing data correctly

**Key technical workflows to monitor:**

| Workflow | Purpose |
|----------|---------|
| **Tracking** | Processes tracking data from email deliveries |
| **Cleanup** | Removes old data and logs to maintain database performance |
| **Deliverability update** | Updates deliverability rules and spam filter patterns |
| **Database cleanup** | Purges old delivery and tracking logs |

Learn more about [technical workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Campaign Control Panel {#control-panel}

Campaign Control Panel provides administrators with self-service capabilities to monitor and manage Campaign instances.

| Monitoring Type | Capabilities |
|-----------------|--------------|
| **Performance** | Track active profile usage, monitor database usage and capacity, view workflow execution status, monitor delivery throughput and latency |
| **Infrastructure** | Monitor SFTP storage capacity, track subdomain configuration, monitor SSL certificate expiration, manage IP allow listing |
| **Instance** | View build version and installed packages, monitor system configuration, manage authorized external domains |

Learn more about [Control Panel](../config/self-service.md) and [Control Panel performance monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html){target="_blank"}

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, Adobe monitors and manages the server infrastructure, operating system, and application layer. You can use the monitoring capabilities described in this page and Control Panel to monitor your instance performance, workflows, and deliveries.

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

* [Delivery best practices](delivery-best-practices.md)
* [Quarantine management](../send/quarantines.md)
* [Configure and send deliveries](../send/configure-and-send.md)
* [Get started with reporting](../reporting/gs-reporting.md)

