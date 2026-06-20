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

Adobe Campaign gives you visibility at every level — from whether an individual message was delivered, to why a workflow failed, to how much database capacity your instance has left. This page maps all monitoring capabilities so you know where to look when something needs attention. As a Campaign administrator, you can also use [Campaign Control Panel](#control-panel) to monitor your instances, manage performance, and configure settings with self-service capabilities.

>[!TIP]
>
>**Not sure where to start?**
>
>- Marketer checking on a campaign → [Monitor your deliveries](#monitor-deliveries)
>- Troubleshooting a workflow → [Monitor workflows](#monitor-workflows)
>- Admin checking instance health → [Monitor your instance](#monitor-instance)

## Monitor your deliveries {#monitor-deliveries}

Monitoring your deliveries after they have been sent is a key step to ensure your marketing campaigns are efficient and reach your customers. After sending a delivery, you can track its progress and diagnose problems from the delivery dashboard. The dashboard gives you access to delivery logs, exclusion logs, tracking logs, and other data for every channel you use.

>[!NOTE]
>
>**New to Campaign?** The delivery dashboard is your main day-to-day screen. Open any sent delivery, click the **Logs** tab, and you will see which recipients received the message, which were excluded and why, and who clicked or opened.

**Email deliveries** — Monitor email delivery status, track key metrics, and access detailed logs. Learn more about [monitoring deliveries in Campaign UI](../send/delivery-dashboard.md), [delivery statuses](../send/delivery-statuses.md) and [email delivery monitoring](../send/send.md#email-monitoring).

**SMS deliveries** — Track SMS delivery status and monitor key metrics in the SMS delivery dashboard. Learn more about [SMS monitoring](../send/sms/sms-monitor.md).

**Push notifications** — Monitor push notification deliveries to ensure they reach your mobile app users effectively. Learn more about [push notification monitoring](../send/push.md#push-test).

**Transactional messages** — For messages triggered by events, monitor event processing status, queue depth, and execution results. Learn more about [transactional message monitoring](../send/delivery-execution.md#monitor-messages).

**Delivery failures** — Understanding why a delivery failed is critical to maintaining a clean database and ensuring good deliverability rates. Delivery failures are classified into three types — understanding the difference helps you decide what action to take:

| Failure type | What it means | What Campaign does |
| --- | --- | --- |
| **Hard bounce** | The address is permanently invalid (does not exist, domain unknown) | Contact is automatically quarantined — it will not be targeted in future deliveries |
| **Soft bounce** | A temporary issue (full mailbox, server temporarily unavailable) | Campaign retries automatically for a configured period |
| **Ignored** | The address was already quarantined or on a blocklist before sending | No attempt is made; counted separately from bounces |

Learn more about [delivery failures and quarantines](../send/delivery-failures.md).

## Monitor deliverability {#monitor-deliverability}

Deliverability is the measure of how successfully your messages reach recipients' inboxes — as opposed to being filtered to spam or rejected. Adobe Campaign provides several built-in tools to help you understand and improve your inbox placement rates.

>[!NOTE]
>
>A message counted as "delivered" means it was accepted by the receiving server — it does not guarantee inbox placement. Deliverability monitoring tells you whether your sending domain authentication, IP reputation, and email content are meeting inbox provider standards.

Adobe Campaign provides the following built-in deliverability tools:

- **Delivery reports** — Built-in reports showing send volume, bounce rates, and unsubscribes over time.
- **Inbox rendering** — Preview how your email appears across major clients (Gmail, Outlook, Apple Mail) before or after sending.
- **SpamAssassin testing** — Score your email content against common spam filter rules to catch issues before delivery.
- **Broadcast statistics** — Aggregate delivery data across your sending volumes and IP reputation.

Following deliverability best practices — such as maintaining a clean email list, monitoring sender reputation, and authenticating sending domains — is critical to maintaining good deliverability rates.

Learn more about [deliverability monitoring tools](../send/monitoring-deliverability.md) and [deliverability best practices](../send/about-deliverability.md).

## Monitor workflows {#monitor-workflows}

Workflows are the engine behind your marketing automations and data processing. Monitoring them ensures that scheduled activities complete as expected and that errors are caught before they affect deliveries or data quality.

>[!TIP]
>
>If a workflow shows a **Failed** status, open it, right-click the red activity, and select **Display logs**. The error message identifies exactly what went wrong and on which record.

### Workflow monitoring capabilities {#workflow-monitoring}

**Monitor the following workflow elements:**

**Workflow execution status** — Track whether workflows are running, paused, failed, or completed. Spot stuck or long-running workflows at a glance. [Learn more about workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

**Activity execution logs** — Drill into per-activity logs to understand what happened at each step — useful for troubleshooting failed transitions or unexpected data outputs.

**Workflow HeatMap** — A visual overview of all workflows running simultaneously across your instance. Use it to identify peak load periods, spot workflows consuming disproportionate resources, and plan scheduling to avoid execution conflicts. Available to Campaign administrators only. [Learn more about workflow heatmap](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html){target="_blank"}

**Workflow history** — Track all workflow executions and modifications over time to understand workflow behavior and performance patterns.

## Monitor your instance {#monitor-instance}

Instance monitoring covers the health of your Campaign environment — database capacity, profile usage, throughput, and infrastructure. For Campaign v8 Managed Cloud Services, Adobe monitors and manages the underlying infrastructure on your behalf, but you retain full visibility through the client console and Control Panel. Learn more about [Adobe-managed monitoring](#adobe-cloud-monitoring).

### Audit trail {#audit-trail}

The Audit trail self-service interface lets you monitor every significant change made within your Adobe Campaign instance. Audit trail captures, in real time, a comprehensive list of actions and events occurring within your instance.

**Use Audit trail to:**

- **Track component changes** — Monitor what happened to your workflows, schemas, options, and other components
- **Identify who made a change** — See which user last modified an element and at what time
- **Troubleshoot unexpected behavior** — Trace back through user actions to find when and how a problem was introduced
- **Support compliance and audits** — Maintain a complete, tamper-evident record of all configuration changes

The Audit trail is accessible through the Campaign client console and provides detailed information about actions performed by users.

Learn more about [Audit trail](../reporting/audit-trail.md)

### Performance monitoring {#performance-monitoring}

Campaign v8 provides several monitoring capabilities to track your instance performance and ensure optimal operation:

**Database monitoring** — Monitor database usage and capacity through Control Panel to ensure optimal performance and storage management. [Learn more about database monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Active profiles monitoring** — Track active profile usage against your contractual limits to maintain compliance and optimize resource allocation. [Learn more about active profiles](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}

**Workflow monitoring** — Monitor workflow execution status to identify long-running workflows and ensure all technical workflows are running correctly. [Learn more about technical workflows](#technical-workflows)

**Delivery throughput and latency** — Track delivery throughput (messages sent per hour) and latency for transactional communications through Control Panel. [Learn more about throughput monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, server infrastructure (CPU, memory, disk) is monitored and managed by Adobe. The monitoring capabilities described on this page and in Control Panel are complementary — they give you visibility into your data and configuration without requiring infrastructure access. Some actions taken by Adobe appear in your Campaign logs under the **campaign-loginmonitor** user. Learn more about [Adobe-managed monitoring](#adobe-cloud-monitoring).

### Adobe-managed monitoring {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services provides mission-critical support for demanding customer experience delivery needs through flexible cloud infrastructure. This lets organizations launch, monitor, and optimize customer experiences without managing or operating Campaign infrastructure themselves.

Adobe monitors your Campaign Cloud Services environments 24/7 to detect technical issues and minimize disruptions. Upon detecting an issue, the system uses auto-restart and auto-launch mechanisms to attempt remediation. If the system does not self-remedy, Adobe On-Call engineering intervenes based on pre-defined alert runbooks.

>[!TIP]
>
>You can subscribe to real-time instance alerts through [Campaign Control Panel](#control-panel) and receive recommended remediation steps for detected issues — for example, SSL certificates nearing expiry.

**Monitoring tiers**

Adobe monitors your environment across three tiers. Tier 1 issues have the widest impact and receive the fastest response:

| Tier | Group | What you may experience |
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
>Adobe Campaign Cloud Services is built on a multi-cloud strategy with deployments on AWS and Azure. Monitoring capabilities differ between AWS, Azure, and other data center deployments. The table above applies to Campaign Cloud Services customers hosted on AWS unless stated otherwise. Adobe Campaign does not currently expose all monitoring data used by On-Call engineering to customers.

### Technical workflows {#technical-workflows}

Technical workflows run silently in the background to maintain your Campaign instance. They are not created by users — they ship with the product. If a technical workflow fails, it can directly affect deliveries and data quality.

Verify that each technical workflow is executing on schedule, completing without errors, and processing data correctly.

| Workflow | Purpose | If it fails |
| --- | --- | --- |
| **Tracking** | Processes tracking data from email deliveries | Click and open metrics stop updating in reports |
| **Cleanup** | Removes old data and logs to maintain database performance | Database grows unchecked, degrading query and delivery performance |
| **Deliverability update** | Updates deliverability rules and spam filter patterns | Rules become stale; filtering accuracy may degrade |
| **Database cleanup** | Purges old delivery and tracking logs | Log accumulation slows queries and reporting over time |

Learn more about [technical workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html){target="_blank"}

### Campaign Control Panel {#control-panel}

Campaign Control Panel provides administrators with self-service capabilities to monitor and manage Campaign instances — without requiring a support ticket.

| Monitoring type | Capabilities |
| --- | --- |
| **Performance** | Active profile usage vs. contract limit, database usage and capacity, workflow execution status, delivery throughput and latency |
| **Infrastructure** | SFTP storage capacity, subdomain configuration, SSL certificate expiry alerts, IP allow listing |
| **Instance** | Build version and installed packages, system configuration overview, authorized external domains |

Learn more about [Control Panel](../config/self-service.md) and [Control Panel performance monitoring](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html){target="_blank"}

>[!NOTE]
>
>For Campaign v8 Managed Cloud Services, Adobe monitors and manages the server infrastructure, operating system, and application layer. The monitoring capabilities described on this page and Control Panel are complementary — they give you visibility into your data and configuration without requiring infrastructure access.

## Tracking and reporting {#tracking-reporting}

### Message tracking {#message-tracking}

Tracking records how recipients interact with your messages after delivery. All tracked events are stored in tracking logs and surfaced in delivery reports.

- **Opens** — Recorded when the tracking pixel loads (email only)
- **Clicks** — Recorded for every tracked link in the message
- **Unsubscribes** — Opt-out requests via the unsubscription link
- **Mirror page views** — Recipients who viewed the email in a browser

Learn more about [message tracking](../send/tracking.md)

### Delivery reports {#delivery-reports}

Adobe Campaign provides a comprehensive set of reports to analyze your delivery performance:

- **Delivery summary** — Overview of sends, deliveries, and failures for a single delivery
- **Tracking indicators** — Opens, clicks, and click-through rates with trend over time
- **URLs and click streams** — Ranking of most clicked links, with counts and percentages
- **Hot clicks** — Visual overlay showing where recipients clicked within the email body

Learn more about [delivery reports](../reporting/delivery-reports.md)

### Global reports {#global-reports}

Access global reports to analyze performance across all campaigns and deliveries:

- **Delivery throughput** — Messages sent per hour across all deliveries over a period
- **Non-deliverables and bounces** — Breakdown of failed deliveries by failure type and reason
- **User activities** — Opens, clicks, and unsubscribes aggregated across all campaigns

Learn more about [global reports](../reporting/global-reports.md)

## Related topics {#related-topics}

- [Delivery best practices](delivery-best-practices.md)
- [Quarantine management](../send/quarantines.md)
- [Configure and send deliveries](../send/configure-and-send.md)
- [Get started with reporting](../reporting/gs-reporting.md)
