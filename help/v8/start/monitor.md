---
title: Campaign monitoring overview
description: Learn how to monitor deliveries, workflows, and your Campaign instance
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Campaign monitoring overview {#monitor-campaign}

Adobe Campaign gives you visibility at every level — from whether an individual message was delivered, to why a workflow failed, to how much database capacity your instance has left. This page maps all monitoring capabilities so you know where to look when something needs attention.

>[!NOTE]
>
>As a Campaign administrator, you can also use [Campaign Control Panel](#control-panel) to monitor your instances, manage performance, and configure settings with self-service capabilities.

>[!TIP]
>
>**Not sure where to start?**
>
>- Marketer checking on a campaign → [Monitor your deliveries](#monitor-deliveries)
>- Troubleshooting a workflow → [Monitor workflows](#monitor-workflows)
>- Admin checking instance health → [Monitor your instance](#monitor-instance)

## Monitor your deliveries {#monitor-deliveries}

Monitoring your deliveries after they have been sent is a key step to ensure your marketing campaigns are efficient and reach out to your customers. After sending a delivery, you can monitor its status and track key metrics in the delivery dashboard. The dashboard provides access to delivery logs, exclusion logs, tracking logs, and other monitoring capabilities to help you analyze your delivery performance across all channels.

>[!NOTE]
>
>**New to Campaign?** The delivery dashboard is your main day-to-day screen. Open any sent delivery, click the **Logs** tab, and you will see which recipients received the message, which were excluded and why, and who clicked or opened.

**Email deliveries** - Monitor email delivery status, track key metrics, and access detailed logs. Learn more about [monitoring deliveries in Campaign UI](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [delivery statuses](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-statuses) and [email delivery monitoring](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**SMS deliveries** - Track SMS delivery status and monitor key metrics in the SMS delivery dashboard. Learn more about [SMS monitoring](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Push notifications** - Monitor push notification deliveries to ensure they reach your mobile app users effectively. Learn more about [push notification monitoring](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test).

**Transactional messages** - For messages triggered by events, monitor event processing status, message execution and delivery status. Learn more about [transactional message monitoring](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Delivery failures** - Understanding why a delivery failed is critical to maintain a clean database and ensure good deliverability rates. Delivery failures are classified into three types — understanding the difference helps you decide what action to take:

| Failure type | What it means | What Campaign does |
| --- | --- | --- |
| **Hard bounce** | The address is permanently invalid (does not exist, domain unknown) | Contact is automatically quarantined — it will not be targeted in future deliveries |
| **Soft bounce** | A temporary issue (full mailbox, server temporarily unavailable) | Campaign retries automatically for a configured period |
| **Ignored** | The address was already quarantined or on a blocklist before sending | No attempt is made; counted separately from bounces |

Learn more about [delivery failures and quarantines](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Monitor deliverability {#monitor-deliverability}

>[!NOTE]
>
>A message counted as "delivered" means it was accepted by the receiving server — it does not guarantee inbox placement. Deliverability monitoring tells you whether your sending domain authentication, IP reputation, and email content are meeting inbox provider standards.

Deliverability monitoring helps you ensure that your messages reach your recipients' inboxes and avoid spam filters. Adobe Campaign provides several built-in tools to monitor and improve deliverability, including delivery reports, inbox rendering, SpamAssassin testing, and broadcast statistics. Following deliverability best practices such as maintaining a clean email list, monitoring sender reputation, and authenticating sending domains is critical to maintain good deliverability rates.

Learn more about [deliverability monitoring tools](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) and [deliverability best practices](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Monitor workflows {#monitor-workflows}

Workflows are essential to automate your marketing campaigns and data processing. Monitoring workflow execution helps you:

- Ensure workflows complete successfully
- Identify and troubleshoot errors
- Optimize workflow performance

>[!TIP]
>
>If a workflow shows a **Failed** status, open it, right-click the red activity, and select **Display logs**. The error message identifies exactly what went wrong and on which record.

### Workflow monitoring capabilities {#workflow-monitoring}

**Monitor the following workflow elements:**

**Workflow execution status** - Track whether workflows are running, paused, failed, or completed. [Learn more about workflow execution](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Activity execution logs** - Access detailed logs for each workflow activity to troubleshoot issues and optimize performance.

**Workflow HeatMap** - A visual overview of all workflows running simultaneously across your instance. Use it to identify peak load periods, spot workflows consuming disproportionate resources, and plan scheduling to avoid execution conflicts. Available to Campaign administrators only. [Learn more about workflow heatmap](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Workflow history** - Track all workflow executions and modifications over time to understand workflow behavior and performance.

## Monitor your instance {#monitor-instance}

Instance monitoring helps you ensure the health and performance of your Adobe Campaign environment. For Campaign v8 Managed Cloud Services, Adobe also monitors and manages the infrastructure on your behalf. Learn more about [Adobe-managed monitoring](#adobe-cloud-monitoring).

### Audit trail {#audit-trail}

The Audit trail self-service interface allows you to monitor changes made within your Adobe Campaign instance. Audit trail captures, in real-time, a comprehensive list of actions and events occurring within your instance.

**Use Audit trail to:**

- **Track component changes**: Monitor what happened to your workflows, schemas, options, and other components
- **Identify who made changes**: See who last updated a specific element and when
- **Understand user actions**: Review what users did in the instance for troubleshooting or auditing
- **Maintain compliance**: Track all configuration changes for compliance and security purposes

The Audit trail is accessible through the Campaign client console and provides detailed information about actions performed by users.

Learn more about [Audit trail](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/audit-trail)

### Performance monitoring {#performance-monitoring}

Campaign v8 provides several monitoring capabilities to track your instance performance and ensure optimal operation:

**Database monitoring** - Monitor database usage and capacity through Control Panel to ensure optimal performance and storage management. [Learn more about database monitoring](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Active profiles monitoring** - Track active profile usage against your contractual limits to maintain compliance and optimize resource allocation. [Learn more about active profiles](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Workflow monitoring** - Monitor workflow execution status to identify long-running workflows and ensure all technical workflows are running correctly. [Learn more about technical workflows](#technical-workflows)

**Delivery throughput and latency** - Track delivery throughput (messages sent per hour) and latency for transactional communications through Control Panel. [Learn more about throughput monitoring](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, server infrastructure (CPU, memory, disk) is monitored and managed by Adobe. Learn more about [Adobe-managed monitoring](#adobe-cloud-monitoring).

### Adobe-managed monitoring {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services provides mission-critical support for demanding customer experience delivery needs through flexible cloud infrastructure. This lets organizations launch, monitor, and optimize customer experiences without the need to manage or operate Campaign infrastructure themselves.

Adobe monitors your Campaign Cloud Services environments to help manage various issues and minimize disruptions by detecting technical issues and providing continuous feedback about performance and ongoing projects.

**How Adobe responds**

Adobe monitors all critical network equipment on the Campaign network 24/7 and receives notifications from monitoring systems when fixes or escalations are needed. Upon detecting an issue, the system uses auto-restart and auto-launch mechanisms to attempt remediation. If the system does not self-remedy, Adobe On-Call engineering intervenes to perform troubleshooting based on pre-defined alert runbooks.

>[!NOTE]
>
>Some monitoring actions performed by Adobe appear in Campaign logs under the **campaign-loginmonitor** user.

In addition to Adobe's internal monitoring, you can access monitoring capabilities directly through the Campaign client console or the [Campaign Control Panel](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service). With Control Panel, you can subscribe to real-time alerts about your instances and receive recommended remediation steps for identified incidents (for example, SSL certificates nearing expiry).

**Monitoring taxonomy**

Adobe monitors your environment across three tiers:

| Tier | Group | Potential business impact |
| --- | --- | --- |
| **Tier 1: Infrastructure** | Database space exhaustion | Performance issues including inability to log in, run batch deliveries, or execute queries |
| **Tier 1: Infrastructure** | Database availability | Users and services may not be able to use the system |
| **Tier 1: Infrastructure** | Database overload (burst balance) | Performance issues including inability to log in, run batch deliveries, or execute queries |
| **Tier 1: Infrastructure** | Database sequence & transaction ID exhaustion | Unable to create new workflows, deliveries, or send batch emails |
| **Tier 1: Infrastructure** | SFTP storage | Unable to update or retrieve data on SFTP servers |
| **Tier 2: Platform and Web** | Login | Users may not be able to log in; scheduled activities and workflows may not execute |
| **Tier 2: Platform and Web** | API lock | Users or services may not be able to authenticate or execute operations |
| **Tier 2: Platform and Web** | Web | Unable to create new connections to Campaign |
| **Tier 2: Platform and Web** | Datacenter network | Performance issues or complete unavailability for users in the datacenter |
| **Tier 3: Software** | Delivery tracking | Processing of tracking logs is unavailable |
| **Tier 3: Software** | inMail | No feedback about errors and bounces of email deliveries |
| **Tier 3: Software** | Message Center status | Unable to send any transactional deliveries |
| **Tier 3: Software** | MTA | Unable to send scheduled and ad-hoc email deliveries |
| **Tier 3: Software** | Workflow server status | Unable to execute workflows |
| **Tier 3: Software** | Web API availability | Unable to process HTTP requests or execute API calls |
| **Tier 3: Software** | Inbound interactions | Unable to process inbound interactions |

>[!NOTE]
>
>Adobe Campaign Cloud Services is built on a multi-cloud strategy and offers deployments on AWS and Azure. Due to vendor differences, monitoring capabilities differ between AWS, Azure, and other data center deployments. The table above applies to Campaign Cloud Services customers hosted on AWS unless stated otherwise. Note also that Adobe Campaign does not currently expose all monitoring data used by On-Call engineering to customers.

### Technical workflows {#technical-workflows}

Technical workflows are essential processes that run in the background to maintain your Campaign instance.

**Monitor that technical workflows are:**

- Executing on schedule
- Completing successfully without errors
- Processing data correctly

**Key technical workflows to monitor:**

| Workflow | Purpose | If it fails |
| --- | --- | --- |
| **Tracking** | Processes tracking data from email deliveries | Click and open metrics stop updating in reports |
| **Cleanup** | Removes old data and logs to maintain database performance | Database grows unchecked, degrading query and delivery performance |
| **Deliverability update** | Updates deliverability rules and spam filter patterns | Rules become stale; filtering accuracy may degrade |
| **Database cleanup** | Purges old delivery and tracking logs | Log accumulation slows queries and reporting over time |

Learn more about [technical workflows](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Campaign Control Panel {#control-panel}

Campaign Control Panel provides administrators with self-service capabilities to monitor and manage Campaign instances.

| Monitoring Type | Capabilities |
| --- | --- |
| **Performance** | Track active profile usage, monitor database usage and capacity, view workflow execution status, monitor delivery throughput and latency |
| **Infrastructure** | Monitor SFTP storage capacity, track subdomain configuration, monitor SSL certificate expiration, manage IP allow listing |
| **Instance** | View build version and installed packages, monitor system configuration, manage authorized external domains |

Learn more about [Control Panel](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) and [Control Panel performance monitoring](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, Adobe monitors and manages the server infrastructure, operating system, and application layer. Learn more about [Adobe-managed monitoring](#adobe-cloud-monitoring). You can use the monitoring capabilities described in this page and Control Panel to monitor your instance performance, workflows, and deliveries.

## Tracking and reporting {#tracking-reporting}

### Message tracking {#message-tracking}

Track recipient behavior and measure the effectiveness of your campaigns:

- **Opens**: Track when recipients open your emails
- **Clicks**: Monitor which links recipients click
- **Unsubscribes**: Track opt-out requests
- **Mirror page views**: See how many recipients view your email in a browser

Learn more about [message tracking](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Delivery reports {#delivery-reports}

Adobe Campaign provides a comprehensive set of reports to analyze your delivery performance:

- **Delivery summary**: Overview of sends, deliveries, and failures
- **Tracking indicators**: Opens, clicks, and click-through rates
- **URLs and click streams**: Most popular links in your deliveries
- **Hot clicks**: Visual representation of where recipients clicked in your email

Learn more about [delivery reports](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Global reports {#global-reports}

Access global reports to analyze performance across all campaigns and deliveries:

- **Delivery throughput**: Messages sent over time
- **Non-deliverables and bounces**: Analysis of failed deliveries
- **User activities**: Opens, clicks, and unsubscribes across all campaigns

Learn more about [global reports](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Related topics {#related-topics}

- [Delivery best practices](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Quarantine management](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Configure and send deliveries](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Get started with reporting](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
