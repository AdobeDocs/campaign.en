---
title: Campaign v8 Frequently Asked Questions
description: Get answers to common Adobe Campaign v8 questions about setup, configuration, messaging, workflows, and more
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, answers, help, support, troubleshooting
version: Campaign v8
hide: yes
hidefromtoc: yes
---
# Frequently Asked Questions {#faq}

Get quick answers to the most common questions about Adobe Campaign v8. Whether you're just getting started or looking for advanced configuration help, you'll find answers organized by topic below.

**New to Campaign?** Start with [General Questions](#general) and [Key Concepts](#key-concepts).  
**Need technical help?** Check [Developers](#developers) and [Campaign Settings](#settings).  
**Can't find your answer?** Visit our [Community Forums](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} or [contact support](#get-help).

**Tip:** Use Ctrl+F (Cmd+F on Mac) to search for specific keywords on this page. Click any question to expand the answer.


## General Questions {#general}

Get answers to the most common questions about Adobe Campaign v8, including how to connect, upgrade, and get support.

+++ How can I connect to Campaign v8?

You need to download and install Campaign client console to connect to Adobe Campaign. [Learn more](connect.md).

Starting Campaign v8.6 release, you have access to the **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. 

Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui). Learn more in the [Adobe Campaign Web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Related topics:**

[Install the client console](connect.md) | [Campaign user interface](campaign-ui.md) | [User permissions](gs-permissions.md)

+++

+++ How to improve email deliverability?

Email deliverability, a critical component to every sender's marketing program success, is characterized by ever-changing criteria and rules. Effectively navigating in this digital world requires regular tuning of your email strategy, with consideration to key deliverability trends, to best reach your audiences.

Refer to this guide to learn [Deliverability Best Practices](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}

Learn how to implement deliverability in Campaign [in this guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html){target="_blank"}

**Related topics:**

[Get started with deliverability](../send/about-deliverability.md) | [Control message content](../send/control-message-content.md) | [Monitor deliverability](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ How can I make sure my delivery is sent without errors?

Follow these steps to ensure successful delivery:

**Before sending:**

* Run delivery analysis to detect errors (missing personalization, invalid recipients, content issues)
* Send test proofs to verify rendering and personalization
* Review warnings during preparation
* Verify target population count

**During and after sending:**

* Monitor the delivery dashboard for real-time statistics (sent, delivered, bounces, errors)
* Check delivery logs for message-level status
* Track success rate, bounce rate, and error messages
* Review quarantined addresses

**Best practices:**

* Set up alerts for error thresholds
* Use waves (batch sending) for large volumes
* Test with small volumes first
* Regularly clean your recipient database
* Monitor sender reputation

Learn more about [monitoring deliveries](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html){target="_blank"} and [delivery best practices](delivery-best-practices.md).

+++

+++ Can I monitor workflow execution?

Yes. Campaign provides several tools to monitor workflow execution:

* **[Workflow dashboard](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}** - View real-time status, progress, and errors for each workflow activity
* **[Workflow logs](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - Access detailed execution logs to troubleshoot issues
* **[Heatmap](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - Visualize workflow activity and identify performance bottlenecks
* **[Audit trail](../reporting/audit-trail.md)** - Track all modifications made to workflows
* **[Alerts](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - Set up notifications for workflow failures or delays

To monitor a workflow, open it and click the **Logs** tab. Failed activities are highlighted in red, and you can view error details by clicking on them.

Learn more about [monitoring workflow execution](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} and [workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}.

+++

+++ How can I download Campaign?

You can get the installation program and the client console from Adobe Download Center.
    
As an Admin user, access Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} to download Adobe Campaign.
    
Learn more about the Distribution Center [on this page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

+++

+++ What is the procedure for domain delegation?

A subdomain is a division of your domain that can be used to isolate your brands, or various types of traffic (transactional messages, marketing information, etc.).
    
>[!NOTE]
>
>As a Managed Cloud Services user, contact Adobe to delegate your subdomains to Adobe.

+++

+++ How can I log an issue?

Creating a case allows you to contact the Adobe Customer Support Team about any issues that you face with your Adobe products. To help resolve or troubleshoot your issues, the Adobe Admin Console will allow you to chat with Adobe Customer Support.

To log an issue or start a chat session in that new system, connect to [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}. 

This system requires individual accounts for each user, with correct permissions. If you find that you can't log in with your Adobe ID, request access via the Experience League, and the Customer Care team will get you set up as soon as possible. [Learn more](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Join Campaign Community: search for answers in existing question or ask the experts. [Join the conversation](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

+++

+++ Which systems and components Campaign v8 is compatible with?

You can get the list of all systems and components supported for the latest build of Campaign in [Adobe Campaign Compatibility matrix](compatibility-matrix.md).

+++

+++ Can I use Campaign v8 with other Adobe solutions?

Yes. Campaign v8 seamlessly integrates with Adobe Experience Cloud solutions to create a powerful, unified marketing ecosystem. As a Managed Cloud Service, v8 is designed for native integration with Adobe's enterprise applications.

**Key integrations available:**

* **Adobe Experience Platform** - Leverage unified customer profiles and real-time data
* **Adobe Analytics** - Measure campaign performance and customer behavior across channels
* **Adobe Target** - Personalize content based on customer segments and behavior
* **Adobe Experience Manager** - Centralize content creation and asset management
* **Adobe Audience Manager** - Build and activate audience segments across platforms

**Benefits:** Unified customer data, consistent user experiences, streamlined workflows, and enhanced personalization capabilities.

**Setup:** Integration with Adobe solutions requires Adobe Identity Management System (IMS) authentication, automatically configured for Campaign v8 Managed Cloud Services.

**Related topics:**

[Adobe Campaign integrations](../connect/integration.md) | [Connect with Adobe ID](connect.md)

+++

+++ What are the limitations of Campaign v8?

Campaign v8 introduces architectural changes (particularly in FFDA deployments) that bring significant performance improvements but also some differences from Campaign Classic v7. Understanding these helps plan migrations and set appropriate expectations.

**Main v8 considerations:**

* **FFDA architecture** - Enterprise deployments use cloud database (Snowflake) with different data access patterns
* **Unit updates** - Data updates should be done in workflows, not through APIs or direct database access
* **Real-time writes** - Optimized for batch operations rather than high-frequency individual updates
* **Data model** - Some schema customizations require different approaches
* **External database access** - FDA (Federated Data Access) configuration differs from v7

**Features not available in FFDA deployments:**

* Surveys (available in standard v8 deployments)
* Marketing Resource Management (MRM)
* Some specific connector configurations

**Migration considerations:**

* Custom code using direct database writes needs refactoring
* API integrations may require adaptation for batch processing
* Workflows should follow FFDA best practices for data operations
* Testing is essential to validate custom developments

**Important:** These limitations are evolving as Adobe continues enhancing v8. Consult the latest documentation for current status and roadmap.

**Related topics:**

[Campaign v7 to v8 migration](../start/v7-to-v8.md#limitations) | [FFDA architecture](../architecture/enterprise-deployment.md)

+++

+++ As a Campaign Classic v7 user, can I migrate to Campaign v8?

Automated migration from an existing Campaign Classic v7 environment is not yet available. 

Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 

For more information about the migration process, reach out to your Adobe representative.

Learn more in the [Campaign v8 vs Previous versions](#v7-differences) section.

+++

+++ What is my version of Campaign?

Check your [version and build number](upgrades.md#version) from the **Help > About...** menu of Campaign client console.

+++

+++ How can I upgrade Campaign to the latest version?

Adobe Campaign is regularly updated. Minor versions are released every year with new features, improvements and fixes. In addition, we periodically release builds with cumulative fixes only.

This regular frequency of updates aims at getting the latest and greatest in your hands, keeping your environment secure and improving your experience with our product. This is the reason why we believe it is critical that you run the most recent version of Adobe Campaign. 

**Note:** As a Managed Cloud Services user, your instance is upgraded by Adobe with new releases.

Learn more about [Campaign versions and upgrades](upgrades.md).

+++

+++ How can I be informed of the release of a new version?

Stay informed about new Campaign releases through these channels:

* **Adobe representative** - Contacts you directly when a new version is available
* **Release Notes** - All versions and changes documented in [Campaign Release Notes](release-notes.md)
* **Adobe Priority Product Updates** - [Subscribe](https://www.adobe.com/subscription/priority-product-update.html){target="_blank"} for email notifications
* **Campaign Community** - Join [discussions](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} for early updates

As a Managed Cloud Services user, Adobe handles upgrades and coordinates timing with you.

**Related topics:**

[Release Notes](release-notes.md) | [What's new](whats-new.md) | [Campaign versions and upgrades](upgrades.md)

+++

+++ Why does my organization need an upgrade?

Upgrading to the latest Campaign version is critical for security, performance, and support quality.

**Key benefits:**

* **Improved security** - Protection against vulnerabilities, latest patches, enhanced data protection
* **Better support** - Faster issue resolution, access to bug fixes, priority support on recent versions
* **Enhanced performance** - Database and workflow optimizations, better scalability, more reliable operations
* **New capabilities** - Latest features, improved Adobe Experience Cloud integrations, modern UI enhancements

Adobe strongly recommends running the most recent version. As a Managed Cloud Services customer, upgrades are performed by Adobe with minimal disruption.

**Related topics:**

[Campaign versions and upgrades](upgrades.md) | [What's new](whats-new.md) | [Compatibility matrix](compatibility-matrix.md)

+++

+++ What is the process and timeline for an upgrade?

As a Managed Cloud Services customer, Adobe manages the entire upgrade process with minimal impact on your operations.

**Process:**

1. **Notification** - Adobe notifies you weeks in advance
2. **Planning** - Schedule upgrade at optimal time with your Adobe representative
3. **Preparation** - Adobe prepares environment and validates
4. **Execution** - Adobe upgrades infrastructure with minimal downtime
5. **Validation** - Post-upgrade testing by Adobe
6. **Client console upgrade** - You upgrade your client consoles to match server version

**Your responsibilities:**

* Coordinate internal stakeholders for timing
* [Upgrade client consoles](connect.md#upgrade-ac-console) to the new version
* Test campaigns and workflows after upgrade
* Report issues to Adobe Support

Adobe performs the infrastructure upgrade. You don't need to perform any technical actions on servers.

**Related topics:**

[Campaign versions and upgrades](upgrades.md) | [Upgrade client console](connect.md#upgrade-ac-console) | [Release Notes](release-notes.md)

+++


## Key Concepts {#key-concepts}

Learn about fundamental Campaign concepts including authentication, user interface, workflows, and core functionalities to get started effectively.

+++ Can I connect to Campaign v8 with an Adobe ID?

Yes! Thanks to the integration with the IMS (Adobe Identity Management System), users connect to the Adobe Campaign console using their Adobe ID. This integration provides the following advantages:

* The same ID can be used for all Experience Cloud solutions.
* The connection is memorized when using Adobe Campaign with different integrations.
* Securer password management policy.
* Use of Federated ID accounts (external ID provider).

[Learn more](connect.md) about accessing Campaign v8 with an Adobe ID.

+++

+++ How can I set up user permissions?

As a Campaign administrator, you can set up permissions for users of your organization.

These are a set of rights and restrictions that authorize or deny to:

* Access to certain functionalities
* Access to certain data
* Create, modify and/or delete data

[Learn more](../start/gs-permissions.md) about user permissions in Campaign v8.

**Related topics:**

[Get started with permissions](gs-permissions.md) | [Manage user permissions](manage-permissions.md) | [Add permissions on folders](folder-permissions.md)

+++

+++ What are Campaign user interface concepts I should know?

Refer to [this section](campaign-ui.md) to learn more about Adobe Campaign user interface basics.

Starting Campaign v8.6 release, you also have access to the new **Campaign Web user interface**, available through the central Adobe Experience Cloud environment.

[Learn more in the Adobe Campaign Web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ How can I select the audience of my messages?

With Adobe Campaign, you can use different strategies to create audiences and select target recipients.

[Learn more](../audiences/gs-audiences.md) about how to define audiences in Campaign v8.

+++

+++ What is a workflow?

Adobe Campaign includes workflows to orchestrate the full range of processes and tasks across the different modules of the application server. This comprehensive graphical environment lets you design processes including segmentation, campaign execution, file processing, human participation, etc. The workflow engine executes and tracks these processes.

You can use a workflow, for example, to download a file from a server, decompress it, and then import records contained within into the Adobe Campaign database.

A workflow can also involve one or more operators to be notified or who can make choices and approve processes. In this way, it is possible to create a delivery action, assign a task to one or more operators to work on content, specify targets, and to approve proofs before starting the delivery.

[Learn more](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"} about workflows. You can also read out [workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}.

**Related topics:**

[Get started with workflows](../config/workflows.md) | [Build your first workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Monitor workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ How to create and send a first email?

Creating your first email in Campaign v8 involves several key steps:

1. **Create the delivery** - Start by creating a new email delivery from a template or from scratch
1. **Define the audience** - Select your target recipients using queries, lists, or workflows
1. **Design the content** - Use the email designer to create your message with personalization
1. **Test with proofs** - Send test emails to validate content and personalization
1. **Analyze and send** - Run delivery analysis to check for errors, then send your email

Campaign v8 offers two interfaces for email creation:

* **Client console** - Full-featured desktop application with advanced capabilities
* **Campaign Web UI** - Modern, intuitive web interface for faster email creation

[Learn more about email design and validation](../send/email.md) in Campaign v8.

**Related topics:**

[Create your first delivery](create-message.md) | [Work with delivery templates](../send/create-templates.md) | [Delivery best practices](delivery-best-practices.md) | [Define the email content](../send/defining-the-email-content.md) | [Preview and proofs](../send/preview-and-proof.md) | [Configure and send](../send/configure-and-send.md) | [Personalize content](../send/personalize.md)

+++

+++ How to send SMS messages?

Sending SMS messages with Campaign v8 requires initial configuration and then follows a straightforward delivery process:

**Initial Setup (one-time configuration):**

1. **Configure SMS channel** - Set up the SMS delivery settings and external account
1. **Configure SMPP connection** - Connect to your SMS service provider via SMPP protocol
1. **Test the connection** - Validate connectivity with your SMS provider
1. **Set up routing** - Define how SMS messages are routed through your provider

**Creating and Sending SMS:**

1. **Create SMS delivery** - Start a new SMS delivery from a template
1. **Define recipients** - Select your mobile audience using phone number fields
1. **Write SMS content** - Create your message (160 characters standard, or longer with concatenation)
1. **Add personalization** - Include dynamic fields specific to each recipient
1. **Send proofs** - Test SMS delivery to validate content and delivery
1. **Analyze and send** - Run analysis and send to your audience

**Key SMS capabilities:**

* **Multiple SMPP connectors** - Support for various SMS providers and protocols
* **Delivery reports** - Track sent, delivered, and failed messages
* **Character encoding** - Support for GSM7, Unicode, and special characters
* **Long SMS support** - Automatic message concatenation for longer texts
* **Two-way SMS** - Handle inbound SMS responses with workflows

[Learn more about SMS configuration and sending](../send/sms/sms.md) in Campaign v8.

**Related topics:**

[Get started with SMS](../send/sms/sms.md) | [SMS delivery settings](../send/sms/sms-delivery-settings.md) | [SMPP external account settings](../send/sms/smpp-external-account.md) | [Create a SMS delivery](../send/sms/create-sms.md) | [SMS content](../send/sms/sms-content.md) | [Send SMS proofs](../send/sms/sms-proofs.md) | [Monitor SMS](../send/sms/sms-monitor.md)

+++

+++ How to send push notifications?

Sending push notifications with Campaign v8 involves configuring your mobile app integration and creating engaging notifications:

**Initial Setup (one-time configuration):**

1. **Configure push channel** - Set up push notification channel settings in Campaign
1. **Integrate Campaign SDK** - Add Adobe Campaign SDK to your mobile app (or use Data Collection)
1. **Configure mobile app** - Register your iOS and Android apps in Campaign
1. **Set up certificates** - Configure APNs certificate (iOS) and FCM key (Android)
1. **Test registration** - Verify devices can register and receive tokens

**Creating and Sending Push Notifications:**

1. **Create push delivery** - Start a new push notification from a template
1. **Select platform** - Choose iOS, Android, or both platforms
1. **Define audience** - Target app subscribers using mobile app subscription data
1. **Design notification** - Create title, message, and rich media content
1. **Configure behavior** - Set click actions, deep links, and custom data
1. **Send test notifications** - Validate on real devices before sending
1. **Analyze and send** - Review targeting and send to your mobile audience

**Push notification capabilities:**

* **Rich push notifications** - Include images, videos, and interactive buttons (iOS and Android)
* **Personalization** - Dynamic content based on user profile and behavior
* **Deep linking** - Direct users to specific app screens or content
* **Scheduling** - Send at optimal times based on user timezone
* **A/B testing** - Test different messages and optimize engagement
* **Tracking** - Monitor opens, clicks, and conversions

**Platform-specific features:**

* **iOS** - Silent notifications, notification categories, sound customization
* **Android** - Rich push templates, notification channels, custom layouts

[Learn more about push notification configuration](../send/push-settings.md) in Campaign v8.

**Related topics:**

[Create and send push notifications](../send/push.md) | [Configure push notification channel](../send/push-settings.md) | [Design an Android rich push](../send/rich-push-android.md) | [Design an iOS rich push](../send/rich-push-ios.md) | [Configure with Data Collection](../send/push-data-collection.md) | [Track and monitor](tracking.md)

+++

+++ How to create landing page?

You can use Adobe Campaign digital content editor to design landing pages and define mapping with database fields.

[Learn more](../dev/landing-pages.md) in Campaign v8 documentation.

You can also use the Campaign Web user interface to create and publish landing pages - [Learn more](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ How can I track deliveries?

You can track deliveries sent with Campaign v8 through dedicated [delivery reports](../reporting/delivery-reports.md) and then monitor your deliveries.

Learn more about tracking management in Campaign [in this page](../start/tracking.md).

**Related topics:**

[Track and monitor messages](tracking.md) | [Delivery reports](../reporting/delivery-reports.md) | [Understand delivery failures](../send/delivery-failures.md) | [Configure tracked links](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"}

+++

+++ How to translate an error message?

An error message is displayed in a foreign language? All error messages and their translation are listed in [this page](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html){target="_blank"}.

+++

+++ Can I create a webform and collect answers in Campaign?

Yes. Create web forms using **Campaign Web Applications & Forms** (client console) for full control over form logic and validation, or use **Campaign Landing Pages** (Web UI) with a modern drag-and-drop interface for subscriptions and lead generation. Both collect data directly into Campaign and integrate with workflows for automated actions.

**Related topics:**

[Learn more about web applications and forms](../dev/webapps.md) | [Campaign Web UI landing pages](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 vs Previous Versions {#v7-differences}

Understand the key differences between Campaign v8 and previous versions (Classic v7 and Standard), including architecture, deployment, migration paths, and feature changes. Whether you're coming from Campaign Classic v7 or Campaign Standard, learn what's new and how to transition smoothly.

+++ Can Campaign v8 be installed on an on-premise or hybrid environment?

No. Campaign v8 is exclusively available as a **Managed Cloud Service**, fully hosted by Adobe.

**Key benefits of Managed Cloud Services:**

* Superior performance and scalability
* Automatic upgrades - always on the latest version
* Enhanced security with continuous monitoring
* No infrastructure management or IT overhead
* Built-in high availability and disaster recovery

Learn more about [Campaign v8 architecture](../architecture/architecture.md) and the [differences between Campaign v8 and Classic v7](../start/v7-to-v8.md).

+++

+++ What are the main differences between Campaign v8 and previous versions?

Campaign v8 is built on a modern cloud-native architecture with significant improvements:

* **Managed Cloud Services only** - Fully hosted by Adobe (no on-premise/hybrid options)
* **Superior performance** - Up to 20 million operations/hour, with Full Federated Data Access (FFDA) architecture
* **New Campaign Web UI** - Modern, intuitive interface alongside the classic console
* **Automatic upgrades** - Always on the latest version with zero downtime
* **Enhanced features** - AI Assistant, rich push notifications, upgraded SMS, improved integrations with Adobe Experience Cloud

**For Campaign Classic v7 users:** Learn about [transitioning from v7 to v8](v7-to-v8.md) including architecture changes, unavailable features, and migration considerations.

**For Campaign Standard users:** Discover the [transition path to v8](acs-to-v8.md) and [Campaign Standard migration guide](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Related topics:**

[Campaign v8 key capabilities](whats-new.md) | [Campaign v8 architecture](../architecture/architecture.md) | [Capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Guardrails and limitations](ac-guardrails.md)

+++

+++ Should I migrate from Campaign Classic v7 or Campaign Standard to v8?

**Campaign v8 is ideal for organizations that need:**

* **High-volume campaigns** - Send millions of messages with improved performance and reliability (20M operations/hour)
* **Enterprise scalability** - Grow your database and campaigns without performance concerns
* **Modern web user interface** - Intuitive, responsive Campaign Web UI for faster campaign creation and improved user experience
* **Cloud-native benefits** - Leverage automatic updates, managed infrastructure, elastic scaling, and proactive monitoring
* **Long-term support** - Campaign v8 is Adobe's strategic platform with extended support, while previous versions will reach End of Support in the coming years
* **Reduced IT overhead** - Eliminate infrastructure management and upgrade planning
* **Advanced capabilities** - AI Assistant, rich push, enhanced SMS, Adobe Experience Platform integration

**For Campaign Standard users:**

Campaign Standard users are now eligible to transition to Campaign v8 Managed Cloud Services. Key benefits include:

* **Familiar interface** - The Campaign Web UI shares many similarities with Campaign Standard, minimizing the learning curve
* **Feature parity** - Key Campaign Standard capabilities have been added to v8 (Dynamic Reporting, Centralized Branding, REST APIs, Landing Pages, Visual Fragments)
* **Enhanced support** - Top-notch assistance with smooth transition and ongoing platform monitoring
* **Data migration** - All your data from Campaign Standard is imported with minimal disruption
* **Consistent user experience** - Continue working with familiar workflows and interface

**For Campaign Classic v7 users:**

Campaign v8 brings substantial improvements while maintaining core Campaign capabilities:

* **Dual interface** - Access both the powerful client console and modern Campaign Web UI
* **Better performance** - Significantly improved query performance and data processing
* **Cloud benefits** - Automatic upgrades, security patches, backup/recovery managed by Adobe
* **Modern architecture** - Enhanced FFDA architecture with PostgreSQL for better scalability

**When to consider migrating:**

* Your current Campaign instance handles large data volumes (millions of profiles)
* You're experiencing performance issues with complex workflows or targeting
* You want to reduce infrastructure management and maintenance costs
* You need seamless integration with Adobe Experience Cloud or Adobe Experience Platform
* You're planning a major upgrade or infrastructure refresh anyway
* **You want future-proof technology** - Previous versions will reach End of Support
* **Your team needs a modern interface** - The Campaign Web UI offers better accessibility for marketers

**Migration considerations:**

* Adobe provides migration support, guidance, and tools
* v8 is Managed Cloud Service only (no on-premise or hybrid deployment)
* Some technical implementations may differ - review the [capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* Data migration and testing require planning and resources
* **For Campaign Standard users** - Transition is designed to be smooth with minimal workflow disruption

**Next steps:**

Contact your Adobe representative to:

* Assess your migration readiness and timeline
* Understand the specific benefits for your use case
* Plan the migration strategy and resource allocation
* Access migration tools and support

**Related topics:**

**For Campaign Classic v7 users:** [From Campaign Classic v7 to v8](v7-to-v8.md) | [v7 to v8 detailed guide](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**For Campaign Standard users:** [Campaign Standard transition to v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Campaign v8 Adoption Guide](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/home){target="_blank"} | [From Campaign Standard to v8 overview](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/overview){target="_blank"} | [Get started for marketers](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/marketers){target="_blank"} | [Get started for admin/developers](https://experienceleague.adobe.com/en/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**General resources:** [Campaign v8 capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Compatibility matrix](compatibility-matrix.md)

+++

+++ How do I migrate my Campaign Classic v7 On-Premise or Hybrid environment to Adobe Managed Services?

Migrating to Adobe Managed Services provides a strategic path from on-premise/hybrid v7 to the cloud, offering improved scalability, security, and reduced IT overhead. It's often a stepping stone before transitioning to Campaign v8.

**Key points:**

* No automated migration tool available - manual planning and execution required
* Adobe Professional Services support highly recommended
* Benefits include cloud infrastructure, automatic security patches, expert support, and easier path to v8
* Migration involves due diligence, environment audit, data cleanup, stage migration, and production cutover

**Getting started:** Contact your Adobe representative to assess your environment and develop a detailed migration plan with Adobe Professional Services.

Learn more about [migrating to Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605){target="_blank"} including challenges, best practices, and detailed migration roadmap.

+++

+++ What are the key terminology and feature differences in Campaign v8?

Campaign v8 brings most Campaign Classic v7 and Campaign Standard capabilities with enhancements, but some features have changes due to the cloud-native architecture, and some terminology differs between versions.

**Terminology differences (Campaign Standard to v8):**

* **Custom resources** are now **Schemas**
* **Messages** are referred to as **Deliveries**
* **Product users** are now **Operators**
* **Roles** are configured with **Named Rights**
* **Security Groups** are now **Operator Groups**
* **Organizational units** are managed through **Folder Permissions**

**Campaign Web UI terminology updates:**

The following terms have been updated in the Campaign Web UI (client console uses traditional terms):

* **Recipients** are now **Profiles**
* **Seed addresses** are now **Test profiles**
* **Delivery analysis** is now **Delivery preparation** (click **Prepare** button)
* **Email Preview** is available through **Simulate content** button
* **Lists** are now **Audiences**

**Not available in v8:**

* **On-premise and hybrid deployments** - v8 is Managed Cloud Services only
* **Direct database access** - Use provided APIs and tools instead
* **Customer-managed infrastructure** - Adobe manages all infrastructure
* **Manual build upgrades** - Now automatic (Adobe managed)

**Different implementations in v8:**

* **Technical workflows** - Some optimized for cloud architecture, may work differently
* **Database structure** - Enhanced FFDA architecture may require schema adaptations
* **Custom integrations** - May need updates for cloud-based architecture
* **Low-level customizations** - Some require different approaches in managed environment

**Enhanced or replaced in v8:**

* **Build upgrades** - Automatic with continuous delivery model instead of manual
* **Performance tuning** - Handled by Adobe infrastructure optimization
* **Security patches** - Applied automatically by Adobe
* **Backup and recovery** - Managed by Adobe as part of service
* **User interface** - New Campaign Web UI alongside client console

**Features added for Campaign Standard users transitioning to v8:**

* **Dynamic Reporting** - Customizable, real-time reports with demographic analysis
* **Centralized Branding** - Define brand visual and technical guidelines
* **REST APIs** - Create integrations and build your ecosystem
* **Landing Pages improvements** - Enhanced feature parity with Campaign Standard
* **Visual Fragments** - Reusable visual components for emails and content templates

**Important:** Most marketing and operational features are available and improved in v8. Technical and infrastructure-level features are managed by Adobe in the cloud environment.

**Related topics:**

[Capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Compatibility matrix](compatibility-matrix.md) | [Guardrails and limitations](ac-guardrails.md) | [v7 to v8 transition guide](v7-to-v8.md)

[Campaign Standard to v8 transition](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Profiles and Audiences {#audiences}

Find answers to questions about managing profiles, creating audiences, importing data, and targeting recipients for your campaigns.

+++ How to create recipients?

Create recipients manually in the client console for individual profiles, import from files (CSV/TXT) for bulk additions, use web forms for self-registration, or integrate via APIs from external systems. Use import workflows for recurring data loads.

**Related topics:**

[Create profiles manually](../audiences/create-profiles.md) | [Import profiles from a file](../audiences/import-profiles.md) | [Collect profiles with web forms](../audiences/collect-profiles.md)

+++

+++ How to import profiles?

Campaign provides multiple import methods: simple file import using the import wizard, workflow-based import for complex transformations, recurring imports with scheduled workflows from SFTP, and API import for programmatic integration.

For file imports, prepare your data file (CSV/TXT, UTF-8 encoding), use the import wizard or workflow, map columns to Campaign fields, define update/insert rules, and test with a small sample first. Use workflows for recurring imports and apply deduplication rules.

**Related topics:**

[Import data guide](../start/import.md) | [Recurring import workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"} | [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}

+++

+++ How can I define the target population of a marketing campaign?

Campaign offers multiple targeting methods: build queries with visual criteria, target existing lists or segments, import recipients from external files (CSV, TXT), or apply pre-defined filters. You can combine criteria with AND/OR logic, exclude specific populations, use control groups, and split for A/B testing. Always preview your target population size before sending.

[Define campaign targets](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"} | [Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Create audiences](../audiences/create-audiences.md)

+++

+++ How can I create a list of profiles?

A list is a static set of recipients that you can target in deliveries and reuse across campaigns.

**Three creation methods:**

* **Manual creation:** Navigate to **[!UICONTROL Profiles and Targets > Lists]** and click **[!UICONTROL Create]**. Add recipients from a query, by individual selection, or from a folder.

* **Workflow automation:** Use the **[!UICONTROL List update]** activity to create and maintain lists automatically from query results or imported data.

* **During import:** Create a list when importing profiles to save them as a reusable group.

**Tip:** Use workflows for lists requiring regular updates, and manual creation for one-time segmentation.

**Related topics:**

[Create audiences](../audiences/create-audiences.md) | [List update activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ How can I deduplicate a population before sending a message?

Use the **[!UICONTROL Deduplication]** activity in a workflow to remove duplicate recipients before delivery. Place it between your **[!UICONTROL Query]** and **[!UICONTROL Delivery]** activities, then choose your deduplication criteria (typically email address or recipient ID) and which record to keep.

**Tip:** Always deduplicate before sending to ensure each person receives your message only once.

Learn more about the [Deduplication activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ How to identify and target subscribers to a newsletter?

Campaign automatically tracks newsletter subscriptions through information services. To target subscribers:

* Use a **[!UICONTROL Query]** activity and filter on **[!UICONTROL Subscriptions]** > select your newsletter service
* Target subscribers directly from your delivery by choosing **[!UICONTROL To > Subscribers of an information service]**
* Build subscriber lists with the **[!UICONTROL Subscription Services]** workflow activity

Campaign tracks subscription/unsubscription history and manages opt-in/opt-out automatically.

**Related topics:**

[Manage subscriptions](../start/subscriptions.md) | [Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ What is the best practice to exclude profiles from a target population?

Use the **[!UICONTROL Exclusion]** activity in a workflow to remove unwanted profiles from your target. Place it after your targeting activities and define which population to exclude.

Learn more about the [Exclusion activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Can I use external profiles without importing them in Campaign?

Yes, Campaign v8 allows you to work with external profiles stored in an external database without loading them into Adobe Campaign. [Learn more](../audiences/external-profiles.md).

+++

+++ How do I create test profiles for my deliveries?

Test profiles are special recipients used to send proofs and validate deliveries without impacting your production database. Create them in **[!UICONTROL Profiles and Targets > Test profiles]**, or use the **[!UICONTROL Seed addresses]** feature to automatically add test recipients to your deliveries for quality assurance and inbox monitoring.

Learn more about [Test profiles](../audiences/test-profiles.md)

+++

## Message Design {#design}

Learn how to design effective marketing messages in Campaign v8, including email templates, personalization techniques, and multilingual content. Design your messages in the client console or use the modern **Email Designer** in the Campaign Web UI for an enhanced visual editing experience.

+++ What are the best practices for designing emails in Campaign?

Key guidelines: ensure mobile-responsive design, use HTML 4.0/XHTML compatible code with inline CSS, optimize images (under 100KB) with alt text, use personalization merge fields, test across email clients before sending, and include a plain text version. Aim for total email size under 500KB for optimal deliverability.

[Email design guide](../send/email.md) | [Delivery best practices](delivery-best-practices.md)

+++

+++ What is a delivery template?

A delivery template is a pre-configured delivery that saves all settings and parameters for reuse across multiple campaigns. Templates include target rules, content design, personalization, technical settings (sender, reply-to), and typology rules. Create once and reuse to maintain consistency and speed up campaign creation.

Learn how to [Create delivery templates](../send/create-templates.md)

+++

+++ Can I easily import an existing HTML to create an email in Campaign?

Yes. Import HTML content via direct copy/paste into the content editor, file upload from your computer, or load from a URL. Ensure your HTML uses email-compatible code (HTML 4.0/XHTML) with inline CSS, and host images on a public server. Campaign automatically adds personalization and tracking to imported HTML.

**Tip:** For the best email design experience, use the **Email Designer** in the Campaign Web UI, which offers modern drag-and-drop capabilities and built-in responsive templates, rather than importing raw HTML.

Learn how to [Import HTML content](../send/defining-the-email-content.md)

+++

+++ How can I create a subscription-based newsletter in Campaign?

Yes. Use Campaign's information services to manage newsletter subscriptions. Key capabilities include automatic opt-in/opt-out handling, subscription tracking, compliance management (GDPR, CAN-SPAM), multi-newsletter support, web integration for sign-up forms, and targeted delivery to subscribers.

Learn how to [manage subscriptions](../start/subscriptions.md)

+++

+++ How can I personalize messages?

Campaign offers personalization capabilities to create relevant, targeted messages based on recipient data, behavior, and preferences.

**Personalization options:**

* **Personalization fields** - Insert recipient data (e.g., `"Hello {{firstName}}")`
* **Personalization blocks** - Use predefined or custom content blocks
* **Conditional content** - Display different content based on recipient criteria
* **Behavioral data** - Leverage browsing history, purchase patterns, or engagement metrics

Test personalization before sending to verify merge fields and conditional logic work correctly.

**Related topics:**

[Personalization guide](../send/personalize.md) | [Personalization fields](../send/personalization-fields.md) | [Conditional content](../send/conditions.md)

+++

+++ Can I send multilingual messages?

Yes. Campaign v8 offers multilingual capabilities, with the **Campaign Web UI** providing the easiest approach. The Web UI offers native multilingual delivery with language variants—add language variants to your delivery, and Campaign automatically sends the appropriate version based on recipient's preferred language. Available for email, push notifications, SMS, and transactional messages.

Key features: automatic content duplication, automatic language-based sending, default language fallback, and easy variant management.

The client console also supports multilingual content using conditional content and workflows, but requires more manual configuration.

[Multilingual deliveries (Web UI)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Conditional content (Client console)](../send/conditions.md)

+++

+++ Can I localize a webform?

Yes. Campaign web applications support multi-language localization. Define translations for all form elements (labels, buttons, messages, error text), with automatic language detection based on recipient profile or browser settings. Multiple language versions are supported within a single web application, with fallback to a default language when needed.

Learn more about [Web application localization](../dev/webapps.md)

+++

+++ Can I use AI-powered content in my emails?

Yes, but **only through the Campaign Web UI**. AI Assistant, powered by Microsoft Azure OpenAI and Adobe Firefly, helps create professional, brand-consistent content across email, SMS, and push notifications.

**Key capabilities:**

* Generate text (email copy, subject lines, SMS/push content) and brand-aligned images
* Create content variations optimized for different audiences
* Refine content (elaborate, summarize, rephrase, simplify)
* Upload brand assets and get brand alignment scoring
* Use existing content as reference and upload style reference images

**Note:** AI Assistant is available exclusively in the Campaign Web UI and currently supports English only. Users need proper permissions and must agree to a user agreement.

[AI Assistant overview](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI Assistant use cases](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Brand alignment](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Testing and Sending Messages {#send}

Learn best practices for testing, validating, sending, and tracking your marketing messages to ensure successful campaign delivery.

+++ What is the delivery analysis?

Delivery analysis is a validation phase Campaign runs before sending. It calculates the target population, validates content, checks for errors, applies typology rules, and estimates delivery volume.

Campaign generates logs showing warnings and errors. Errors block delivery and must be fixed; warnings are advisory. Always review analysis logs before sending.

Learn more in the [Delivery analysis guide](../send/delivery-analysis.md)

+++

+++ Why should I create proofs?

Proofs are test messages that validate your delivery before sending to your main audience. Use proofs to verify personalization, test content rendering across email clients, confirm links and tracking work, check images and attachments, and validate mobile responsiveness.

Proofs help catch errors before they reach thousands of recipients, enable stakeholder approval, and test inbox placement. Send proofs to multiple email clients and devices, and always obtain approval before production sends.

Learn more in the [Proofs and preview guide](../send/preview-and-proof.md)

+++

+++ How to use seed addresses in Adobe Campaign?

Seed addresses are special recipients automatically added to every delivery for testing, quality assurance, and monitoring—without matching your target criteria. Useful for ongoing monitoring, inbox placement testing, direct mail validation, and stakeholder visibility.

**Key differences from proofs:**

* **Seed addresses** - Added to production deliveries automatically, count toward send volume
* **Proofs** - Test sends before production, don't count toward volume, used for validation

Manage seed addresses in **[!UICONTROL Resources > Campaign management > Seed addresses]**. Keep lists small to avoid impacting delivery metrics.

[Seed addresses guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ How can I set up an approval process before sending messages?

Campaign provides approval workflows to ensure messages meet quality standards before sending. Configure approvals for content, target, extraction (direct mail), and budget at the campaign or delivery level.

**Setup:**

Create operator groups in **[!UICONTROL Administration > Access management > Operator groups]**, then assign approval groups in campaign or delivery properties. Campaign sends notification emails to reviewers who can approve, reject, or request changes.

**For standalone deliveries (not in a campaign):**

Use **proofs as your approval process**. Send proofs to your approval group for validation, and always send a new proof after making changes to ensure stakeholders review the latest version.

**Related topics:**

[Delivery validation](../send/preview-and-proof.md) | [Campaign approvals](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"}

+++

+++ What is a typology rule?

Typology rules are automated business logic applied during delivery analysis to validate and optimize message sending. They ensure compliance with marketing policies, protect deliverability, and prevent customer fatigue.

**Main rule types:**

* **Filtering rules** - Exclude recipients (blocklisted, unsubscribed, quarantined)
* **Pressure rules** - Control message frequency to avoid overwhelming recipients
* **Capacity rules** - Limit message volume for processing capacity or ISP limits
* **Control rules** - Check message validity (subject line, unsubscribe link, sender format)

Rules are grouped into typologies and applied during delivery analysis. Campaign can exclude recipients, block the delivery, or generate warnings based on the rules.

[Typology rules guide](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html){target="_blank"}

+++

+++ How can I send emails in waves?

Yes. Wave sending splits your delivery into multiple batches sent at scheduled intervals. This is essential for large-volume campaigns to balance server load, prevent ISP throttling, build sender reputation with new IPs, and manage opt-outs/bounces between waves.

**Configuration:**

In your delivery properties, enable wave sending and define the number of waves (or batch size), interval between waves, and wave distribution (linear or custom percentages). Campaign automatically divides your target population and sends each wave on schedule.

Use waves for large campaigns, monitor first wave performance before continuing, and allow sufficient time between waves to process bounces and opt-outs.

Learn how to [Configure wave sending](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Which are the key steps to create an email in Campaign?

Creating an email in Campaign v8 involves these key steps: create the delivery, define the target audience, design the content, add personalization, configure settings (sender, subject, reply-to), run delivery analysis, send proofs for testing, and finally send or schedule.

**Key steps:**

1. **Create the delivery** - Choose email as the channel and optionally select a delivery template
1. **Define the target** - Select your recipient audience using queries, lists, or imported files
1. **Design the content** - Create your message using the email editor (Web UI Email Designer or client console editor)
1. **Add personalization** - Insert dynamic fields, personalization blocks, and conditional content
1. **Configure settings** - Set sender address, subject line, reply-to, and delivery parameters
1. **Run delivery analysis** - Campaign validates content, calculates the target, and checks for errors
1. **Send proofs** - Test your email with approval groups to validate rendering and content
1. **Send or schedule** - Send immediately to the main target or schedule for a later date

**Two interface options:**

* **Campaign Web UI** - Modern interface with enhanced Email Designer, AI Assistant, and multilingual capabilities
* **Client console** - Traditional interface with advanced targeting and workflow capabilities

**Tip:** Use the Campaign Web UI for faster, more intuitive email creation with modern design tools. Use the client console for complex targeting or advanced workflow-based campaigns.

**Related topics:**

[Create your first email](create-message.md) | [Email design guide](../send/email.md)

+++

+++ How to schedule a delivery?

Campaign allows you to schedule deliveries for future sending to optimize send times and coordinate campaigns.

**Scheduling options:**

* **Delivery properties** - Send immediately, schedule for specific date/time, or defer by hours/days
* **Campaign level** - Coordinate all deliveries within a campaign
* **Workflow Scheduler activity** - For recurring deliveries, complex patterns, and event-triggered campaigns

Campaign also supports contact date optimization (best send time per recipient) and time zone adaptation (same local time for all recipients).

Learn how to [Schedule delivery sending](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Can I add an attachment to emails?

Yes. Campaign supports static attachments (same file for all recipients) and personalized attachments (different files per recipient based on profile data). Add attachments in the **[!UICONTROL Attachments]** section of your delivery properties.

**Important considerations:**

* Keep attachments under 1MB for optimal deliverability
* Attachments can trigger spam filters; test thoroughly before sending
* Avoid file types commonly blocked by email clients (.exe, .zip, .js)
* For large files, consider using tracked download links instead

Use safe file formats (PDF, JPEG, PNG, DOCX) and test with seed addresses before production sends.

Learn more in the [Email attachments guide](../send/email.md#attachments)

+++

+++ How can I configure tracked links in an email delivery?

Campaign automatically converts all URLs in your email into tracked links to monitor recipient engagement. Access the **[!UICONTROL Tracking]** section in your delivery to configure tracking settings for each link.

**Configuration options:**

* **Enable/disable tracking** - Control tracking per link
* **Link labels** - Add descriptive names for reporting (e.g., "Shop Now CTA")
* **Link categories** - Group links by type for aggregated analysis
* **Tracking type** - Track clicks, opens, or both

Campaign tracks content links, mirror page links, unsubscribe links, and can include an optional tracking pixel for email opens. Use meaningful labels and categories to simplify reporting and quickly identify high-performing content.

**Related topics:**

[Link tracking guide](../start/tracking.md) | [Tracking best practices](../send/send.md)

+++

+++ Where can I access delivery and tracking logs?

Access delivery and tracking logs directly from each delivery dashboard. In the client console, click the **[!UICONTROL Delivery]** tab at the bottom. In the Campaign Web UI, navigate to the **[!UICONTROL Logs]** section.

**Available logs:**

* **Delivery logs** - Sent messages with recipient details and status (sent, pending, failed)
* **Tracking logs** - Recipient interactions (opens, clicks) with timestamps
* **Exclusion logs** - Excluded recipients with reasons (quarantine, typology rules, duplicates)
* **Broadcast logs** - Complete sending history including retries and errors

Use these logs to troubleshoot delivery issues, analyze engagement, and maintain list hygiene.

**Related topics:**

[Delivery monitoring](../send/send.md) | [Tracking guide](../start/tracking.md)

+++

+++ Where can I get delivery reports?

Campaign provides comprehensive built-in reports to analyze delivery performance, recipient engagement, and campaign effectiveness. Access reports from the **[!UICONTROL Reports]** tab in any delivery, from the campaign dashboard, or from the global **[!UICONTROL Reports]** menu for cross-campaign analysis.

**Key reports include:**

* **Delivery summary** - Send statistics, opens, clicks, bounces, and unsubscribes
* **Hot clicks** - Visual heatmap of link performance
* **Tracking indicators** - Click-through rates and engagement metrics
* **Non-deliverables** - Bounce analysis with failure reasons

Reports are available in both the client console and Campaign Web UI with modern visualizations.

**Related topics:**

[Built-in delivery reports](../reporting/delivery-reports.md) | [Campaign reporting](../reporting/gs-reporting.md)

+++

+++ How does Adobe Campaign qualify and manage quarantine addresses?

Campaign automatically manages a quarantine list to protect your sender reputation and improve deliverability. Quarantined addresses are automatically excluded from future deliveries until they're validated or removed from quarantine.

**Why addresses get quarantined:**

* **Hard bounces** - Permanent delivery failures (invalid email address, domain doesn't exist, mailbox deleted)
* **Soft bounce threshold** - Repeated temporary failures (mailbox full, server temporarily unavailable) exceeding the error threshold
* **Spam complaints** - Recipients marking your emails as spam
* **Invalid addresses** - Addresses with syntax errors or that fail validation
* **Blocklisted** - Recipients who opted out or requested to be excluded

**How quarantine works:**

Campaign tracks delivery errors for each address. When an address reaches the configured error threshold, it's automatically quarantined and excluded from all future deliveries during analysis. Hard bounces (permanent failures) are quarantined immediately, while soft bounces require multiple failures before quarantine.

**Managing quarantined addresses:**

Access quarantine management in **[!UICONTROL Administration > Campaign Management > Non deliverables Management]**. You can view quarantined addresses, manually remove validated addresses from quarantine, or configure automatic cleanup rules.

**Tip:** Monitor your quarantine list regularly. Increasing quarantine rates often signal data quality issues that need attention before they impact sender reputation.

**Related topics:**

[Quarantine management guide](../send/quarantines.md) | [Bounce management](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Explore how to use workflows to automate processes, manage data, and orchestrate complex marketing campaigns in Adobe Campaign.

+++ What are the key steps to create a workflow?

Create workflows to automate marketing processes in Campaign:

1. **Create a new workflow** - Navigate to **[!UICONTROL Profiles and Targets > Jobs > Targeting workflows]** or **[!UICONTROL Administration > Production > Technical workflows]** and click **[!UICONTROL Create]**
1. **Add activities** - Drag and drop activities from the palette (targeting, flow control, action activities)
1. **Configure activities** - Double-click each activity to set parameters and define logic
1. **Connect activities** - Link activities with transitions to define the execution flow
1. **Test and validate** - Use the workflow diagram to check logic, then test with a small dataset
1. **Execute** - Start the workflow manually or schedule it for automatic execution

Common workflow patterns: data import, audience segmentation, delivery sending, data enrichment, and cross-channel orchestration.

**Related topics:**

[Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Workflow activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ How can I import data in Campaign?

Import data into Campaign using multiple methods depending on your needs:

**Simple file import:**

* Use the import wizard for one-time CSV/TXT imports with a guided interface
* Ideal for manual uploads and quick data loads

**Workflow-based import:**

* Create workflows with **[!UICONTROL Data loading (file)]** activity for complex imports
* Add data transformations, enrichment, and deduplication
* Schedule recurring imports from SFTP, local directories, or cloud storage

**API integration:**

* Use REST APIs to import data programmatically from external systems
* Ideal for real-time synchronization with CRM, e-commerce, or other platforms

**Best practices:** Always test with small samples, use UTF-8 encoding, map fields correctly, apply deduplication rules, and schedule large imports during off-peak hours.

**Related topics:**

[Import best practices](../start/import.md) | [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Recurring import workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ What are common workflow use cases in Campaign?

Campaign workflows can automate virtually any marketing process. Here are the most common use cases:

**Data management:**

* **Import and load data** - Automate file imports from SFTP, API, or cloud storage
* **Data cleansing** - Deduplicate profiles, standardize formats, remove invalid records
* **Data enrichment** - Enhance profiles with external data or calculated fields
* **List management** - Automatically update segments based on behavior or criteria

**Campaign automation:**

* **Welcome series** - Trigger automated onboarding emails for new subscribers
* **Birthday campaigns** - Send personalized messages on customer birthdays or anniversaries
* **Re-engagement** - Target inactive subscribers with win-back campaigns
* **Cart abandonment** - Send reminders to customers who left items in cart

**Advanced targeting:**

* **A/B testing** - Split audiences and test different content variations
* **Dynamic segmentation** - Create segments based on real-time behavior or attributes
* **Lead scoring** - Calculate and update lead scores based on engagement
* **Cross-channel orchestration** - Coordinate messaging across email, SMS, and push

**Monitoring and alerts:**

* **Workflow monitoring** - Track workflow status and send alerts on failures
* **Delivery monitoring** - Monitor campaign performance and bounce rates
* **Database maintenance** - Automate cleanup of old logs and temporary data

**Integration and synchronization:**

* **CRM sync** - Keep customer data synchronized with Salesforce, Dynamics, etc.
* **API integrations** - Connect with e-commerce platforms, analytics tools, or custom systems
* **Event-triggered workflows** - React to real-time events from websites or apps

**Related topics:**

[Workflow use cases library](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Targeting workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"} | [Data management workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/about-data-management.html){target="_blank"}

+++

+++ How can I update Campaign data with a workflow?

Use the **[!UICONTROL Update data]** activity in workflows to perform bulk operations on your database:

**Supported operations:**

* **Insert** - Add new records to the database
* **Update** - Modify existing records based on matching criteria
* **Insert or update** - Add new records or update existing ones (upsert)
* **Delete** - Remove records matching specific criteria

**Common use cases:**

* Update profile attributes after data enrichment
* Synchronize data with external systems
* Maintain list memberships based on behavior
* Clean and deduplicate data
* Apply bulk status changes (e.g., opt-out, quarantine)

Configure reconciliation keys to match records accurately and choose update options (update all fields or only empty ones).

**Related topics:**

[Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ How can I leverage data management capabilities?

Campaign's data management activities enable sophisticated data operations within workflows for complex targeting and segmentation.

**Key data management activities:**

* **Enrichment** - Add data from related tables or external sources to your working population
* **Split** - Segment populations based on criteria or distribute randomly
* **Deduplication** - Remove duplicate records based on specified keys
* **Update data** - Perform bulk insert, update, or delete operations
* **Change dimension** - Switch targeting dimensions (e.g., from recipients to subscriptions)
* **Intersection/Union/Exclusion** - Combine or filter multiple populations

**Common use cases:**

* Enrich profiles with purchase history or behavior data
* Segment audiences into multiple groups for different messages
* Remove duplicates before delivery
* Integrate data from external databases (FDA - Federated Data Access)
* Create complex multi-table queries and joins

These activities allow you to work with data not directly in the main recipient table and perform advanced database operations.

**Related topics:**

[Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Targeting workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"} | [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Can I automate personalized messages sending?

Yes. Workflows enable fully automated personalized message campaigns based on recipient data, behavior, and custom criteria.

**Automation workflow structure:**

1. **Query** - Select your target audience based on criteria
1. **Enrichment** - Add personalization data from related tables
1. **Split** - Segment into groups for different message variants (optional)
1. **Delivery** - Send personalized messages with merge fields
1. **Scheduler** - Set up recurring execution for automated campaigns

**Personalization options:**

* Use recipient profile data (name, location, preferences)
* Include behavioral data (purchase history, engagement scores)
* Apply conditional content based on segments or attributes
* Calculate dynamic values (loyalty points, expiration dates)

Common scenarios: birthday campaigns, cart abandonment, loyalty programs, win-back campaigns, and event-triggered messages.

**Related topics:**

[Personalization guide](../send/personalize.md) | [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"} | [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ How can I split an audience in subsets with a workflow?

Use the **[!UICONTROL Split]** activity to divide a single population into multiple subsets based on criteria or distribution rules.

**Split methods:**

* **Filtering conditions** - Create subsets based on criteria (e.g., age groups, location, VIP status)
* **Percentage distribution** - Split randomly into equal or custom percentages for A/B testing
* **Limit records** - Restrict subset sizes (first N records, top X%, random selection)
* **Data grouping** - Create one subset per distinct value (e.g., one subset per country)

**Common use cases:**

* A/B testing with control groups
* Channel preference routing (email vs. SMS)
* Progressive rollout (send to 10%, then 90%)
* Segment-specific messaging (VIP, regular, new customers)
* Load balancing across multiple delivery servers

Each split subset flows to a separate transition, allowing different processing or delivery for each group.

**Related topics:**

[Split activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [A/B testing guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ How can I update recipient data from an external file?

Yes. Use workflows to update Campaign data with values from external files (CSV, TXT).

**Workflow structure:**

1. **Data loading (file)** - Load the external file and map columns
1. **Enrichment** (optional) - Add additional data or transformations
1. **Reconciliation** - Define keys to match file records with database records (e.g., email address, recipient ID)
1. **Update data** - Choose update options:
   * Update matched records only
   * Update existing fields or only empty ones
   * Insert new records if no match found

**Common scenarios:**

* Update profile attributes from CRM exports
* Refresh subscription statuses from external systems
* Synchronize loyalty points or customer scores
* Update opt-in/opt-out preferences
* Enrich profiles with behavioral data

**Best practices:** Use unique identifiers for reconciliation, validate data before update, test with small samples, and schedule regular updates for ongoing synchronization.

**Related topics:**

[Import data guide](../start/import.md) | [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ How can I identify and target new recipients?

Use workflows with query activities to identify recently added recipients and trigger automated welcome campaigns.

**Query approach:**

Create a query filtering on the **[!UICONTROL Created date]** field to select recipients added within a specific timeframe (e.g., last 24 hours, last week).

**Automated welcome workflow structure:**

1. **Scheduler** - Run daily or at specific intervals
1. **Query** - Select recipients created since last execution
1. **Deduplication** (optional) - Ensure no duplicates
1. **Delivery** - Send welcome message
1. **Update data** (optional) - Mark recipients as "welcomed"

**Advanced technique with aggregates:**

Use aggregate functions to dynamically identify the most recent additions and compare against previously processed recipients for sophisticated new recipient detection.

**Related topics:**

[Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Using aggregates](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"} | [Welcome programs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}

+++

+++ How do I use workflow activities?

Campaign workflows are built using four main categories of activities, each serving specific purposes:

**Targeting activities** - Define and refine your audience

* Query, Split, Deduplication, Enrichment, Intersection, Union, Exclusion
* Use these to select recipients, segment populations, and combine data sources

**Flow control activities** - Manage workflow logic and timing

* Scheduler, Wait, Test, Fork, AND-join, OR-join, Jump
* Control execution flow, add conditions, and manage parallel paths

**Action activities** - Perform operations and send messages

* Delivery, Update data, Data loading (file), Data extraction (file), JavaScript code
* Execute database operations, file transfers, and message sending

**Event activities** - React to external triggers

* External signal, File collector, HTTP transfer, SMS, Email
* Handle incoming data and external system interactions

To use activities, drag them from the palette to your workflow canvas, double-click to configure parameters, and connect them with transitions.

**Related topics:**

[Targeting activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [Flow control activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [Action activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"} | [Event activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

+++

+++ What are workflow best practices?

Follow these best practices to build efficient, maintainable, and reliable workflows:

**Design and organization:**

* Use clear, descriptive names for workflows and activities
* Add labels and descriptions to document logic
* Group related activities visually for readability
* Break complex processes into multiple smaller workflows

**Performance optimization:**

* Limit query result sizes with appropriate filters
* Use temporary tables for intermediate data storage
* Schedule resource-intensive workflows during off-peak hours
* Avoid unnecessary loops and excessive iterations

**Error handling and monitoring:**

* Add error handling paths with supervisors
* Configure alerts for failed workflows
* Test with small data samples before full execution
* Review execution logs regularly for performance issues

**Maintenance and governance:**

* Archive or delete obsolete workflows
* Version control workflow changes and document modifications
* Limit workflow complexity (aim for < 20 activities)
* Use workflow templates for recurring patterns

**Security and data management:**

* Apply appropriate operator permissions
* Clean up temporary data with workflow cleanup
* Avoid hardcoding values—use variables and options
* Regularly review and optimize poorly performing workflows

**Related topics:**

[Workflow best practices guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Monitor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campaign Settings {#settings}

Configure your Campaign instance with the right settings, integrations, and configurations to optimize your marketing operations.

+++ Can I change the language of Campaign interface?

It depends on which interface you're using. The **client console** language is fixed, but the **Campaign Web UI** allows individual users to change their language preferences.

**Client Console (Desktop Application):**

* Language is set when your instance is created and cannot be changed
* The client console and server must use the same language
* Each Campaign instance operates in a single language
* For English installations, you can choose between US English or UK English (they differ in date and time formats)

**Campaign Web UI:**

* Users can change their interface language independently through their profile preferences
* Multiple languages are supported with locale-specific formatting for dates, times, and numbers
* Your Web UI language preference is independent of your Campaign server and client console language


**Related topics:**

[Change language in Campaign Web UI](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Get started with Campaign client console](connect.md)

+++

+++ What is Campaign Control Panel and how do I access it?

Campaign Control Panel is a web-based administrative interface that helps Campaign administrators increase efficiency by managing settings and monitoring usage across Campaign instances. It provides self-service capabilities to manage critical instance configurations without contacting Adobe Support.

**Key capabilities:**

* **Subdomain management** - Delegate and manage subdomains, monitor SSL certificates
* **Storage monitoring** - Track database usage and prevent storage issues
* **SFTP management** - Monitor SFTP storage, manage IP allowlists, and SSH keys
* **Instance settings** - Configure IP allowlists, manage URL permissions, review instance details
* **Active profiles monitoring** - Track active profile usage against entitlements
* **Performance monitoring** - Monitor database and workflow performance
* **Email deliverability** - Configure DMARC, BIMI, and other authentication records

**Access requirements:**

* **Admin users only** - Control Panel is restricted to users with Administrator rights
* **Adobe IMS authentication** - Access through Adobe Experience Cloud with your Adobe ID
* **Campaign v8 Managed Cloud Services** - Available for hosted instances only

**Additional resources:** 

[Control Panel documentation](https://experienceleague.adobe.com/en/docs/control-panel/using/control-panel-home){target="_blank"} | [Control Panel tutorial videos](https://experienceleague.adobe.com/en/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ How can I set up tracking capabilities on my Campaign instance?

Campaign v8 provides comprehensive tracking to monitor recipient interactions with your messages. Tracking requires proper configuration of your instance and message settings.

**What you can track:**

* **Email opens** - Via tracking pixel (1x1 transparent image)
* **Link clicks** - All URLs automatically converted to tracked links
* **Unsubscribes** - Opt-out link tracking
* **Mirror page views** - When recipients view the web version
* **Custom parameters** - Add tracking data to URLs for advanced analysis

**Key configuration steps:**

1. Configure tracking server URL in your instance settings (managed by Adobe for v8)
2. Enable tracking in delivery properties
3. Set up tracking for individual links or all links automatically
4. Define tracking validity period and log retention

**Best practice:** Always test tracking with proofs before sending to your main audience to ensure links work correctly and data is captured.

**Related topics:**

[Track and monitor deliveries](tracking.md) | [Configure tracked links](../send/email.md)

+++

+++ How to configure email deliverability?

Email deliverability depends on technical configuration, content quality, and sender reputation. Campaign v8 provides tools and settings to optimize inbox placement.

**Essential configuration steps:**

* **Domain authentication** - Set up SPF, DKIM, and DMARC records to verify your sending domain
* **IP warming** - Gradually increase sending volume on new IPs to build reputation
* **Sender configuration** - Use consistent, recognizable sender addresses and names
* **Bounce management** - Configure quarantine rules to handle hard and soft bounces automatically
* **Feedback loops** - Set up complaint handling to manage spam reports

**Content best practices:**

* Test emails with SpamAssassin to check spam score
* Maintain proper text-to-image ratio
* Include plain text version alongside HTML
* Always provide unsubscribe link
* Avoid spam trigger words and excessive capitalization

**Monitoring:** Use Campaign's deliverability reports to track bounce rates, complaint rates, and inbox placement. For Campaign v8, Adobe provides infrastructure-level deliverability optimization.

**Related topics:**

[About deliverability in Campaign](../send/about-deliverability.md) | [Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}

+++

+++ Which external databases can I connect Campaign to?

Campaign v8 supports Federated Data Access (FDA) connections to major enterprise database systems, enabling you to leverage existing data infrastructure.

**Supported databases:**

* **Cloud databases:** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Enterprise databases:** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Data warehouses:** Teradata, Vertica, SAP HANA
* **Big data:** Hadoop via Hive

**Platform-specific considerations:** Supported database versions and connection requirements vary. Campaign v8 as a Managed Cloud Service may have specific network and security requirements for external database access.

**Important:** Always check the official compatibility matrix for your Campaign v8 version to confirm support for specific database versions and ensure proper licensing for external database connectors.

**Related topics:**

[Compatibility matrix](compatibility-matrix.md) | [Configure FDA connections](../connect/fda.md)

+++

+++ Can Adobe Campaign integrate with CRM systems?

Yes. Campaign provides native CRM connectors for seamless bidirectional synchronization between Campaign and your CRM system, ensuring consistent customer data across platforms.

**Supported CRM systems:**

* **Salesforce** - Leads, contacts, accounts, opportunities, campaigns
* **Microsoft Dynamics 365** - Contacts, accounts, leads, custom entities
* Other CRMs via custom API integrations

**What syncs:**

* **From CRM to Campaign:** Contact records, account information, leads, custom fields, segmentation data
* **From Campaign to CRM:** Delivery logs, tracking data, engagement metrics, campaign responses, subscription status

**Synchronization modes:**

* **Scheduled** - Automatic sync at defined intervals (hourly, daily)
* **Manual** - On-demand sync triggered by operators
* **Real-time** - Via API for immediate updates (custom development)

**Configuration:** Use Campaign's built-in CRM connector assistant to map CRM fields to Campaign attributes, select tables to sync, and schedule synchronization. The connector handles conflict resolution and maintains data consistency.

**Best practice:** Start with read-only sync to test mapping, then enable bidirectional sync. Monitor sync logs for errors and maintain clean data in both systems.

**Related topics:**

[CRM connector configuration](../connect/crm.md) | [Workflow CRM activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html){target="_blank"}

+++

+++ How do I clear the client console cache?

Clearing the client console cache resolves many common display and functionality issues. The cache stores local configuration files that can sometimes become corrupted or outdated.

**When to clear cache:**

* New branding elements (logos, colors) not displaying correctly
* Export/import functions failing unexpectedly
* Interface elements not updating after configuration changes
* Performance issues or slow console response
* After upgrading to a new client console version

**Steps to clear cache:**

1. Open the Campaign client console
2. Go to **[!UICONTROL File]** menu
3. Select **[!UICONTROL Clear the local cache...]**
4. Confirm the action when prompted
5. Restart the client console

**Related topics:**

[Install and configure client console](connect.md)

+++

+++ Can I configure user interface settings?

Yes. Campaign administrators can customize the user interface to match organizational branding and optimize user experience. Configure settings at the instance or user level.

**What you can customize:**

* **Branding** - Logo, colors, and visual identity elements
* **Default views** - Home page layout, folder structure visibility
* **List configurations** - Default columns, sort order, filters in data lists
* **Navigation** - Available menu items and shortcuts
* **Regional settings** - Date/time formats, number formats, time zones
* **Notifications** - Email alerts, in-app notifications, workflow alerts

**Configuration levels:**

* **Instance-wide** - Apply to all users (requires administrator rights)
* **User-specific** - Individual preferences and personal settings
* **Operator group** - Settings inherited by all group members

**Related topics:**

[Configure UI settings](../config/ui-settings.md) | [User permissions](gs-permissions.md)

+++

+++ Can I create custom fields and tables?

Yes. Campaign's flexible data model allows you to extend built-in schemas with custom fields and create entirely new tables to meet your specific business needs.

**What you can customize:**

* **Add fields to existing tables** - Extend recipient table with loyalty points, custom preferences, external IDs
* **Create new custom tables** - Store products, transactions, loyalty tiers, custom entities
* **Define relationships** - Link custom tables to existing Campaign tables
* **Extend forms** - Update UI to display and edit custom fields

**Common use cases:**

* Store additional profile attributes (customer lifetime value, preferred store, VIP status)
* Manage product catalogs with custom attributes
* Track custom events and interactions
* Integrate external system IDs for data synchronization
* Build industry-specific data models (retail, finance, travel)

**Related topics:**

[Extend data model](../dev/extend-schema.md) | [Schema structure](../dev/schemas.md) | [Data model best practices](../dev/datamodel-best-practices.md)

+++

## Reporting {#reporting}

Get insights into Campaign's reporting capabilities, including built-in reports, custom reports, and data analysis tools like cubes.

+++ How can I create new reports?

Campaign offers multiple reporting options depending on your needs and technical expertise. You can use built-in reports, create custom reports in the client console, or design visual dashboards in the Campaign Web UI.

**Reporting options:**

* **Built-in reports** - Ready-to-use delivery, campaign, and tracking reports accessible from the **[!UICONTROL Reports]** tab
* **Descriptive analysis** - Quick statistical reports on any data with a wizard-driven interface
* **Custom reports** - Advanced reports built by technical users using the reporting editor
* **Web UI dashboards** - Modern visual reports and dashboards with drag-and-drop interface
* **Cubes** - Multi-dimensional data exploration and pivot table analysis

**Important:** Campaign is designed for marketing operations reporting, not as a specialized business intelligence tool. For complex analytical needs, consider integrating with Adobe Analytics or dedicated BI platforms.

**Related topics:**

[Get started with reporting](../reporting/gs-reporting.md) | [Campaign Web UI reports](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ How can I design and share statistic reports on populations?

Use Campaign's descriptive analysis tool to quickly generate statistical reports on any population data. This wizard-driven feature helps you analyze distributions, trends, and patterns without technical expertise.

**What you can analyze:**

* Recipient demographics and segmentation breakdowns
* Campaign performance metrics and response rates
* Distribution of profile attributes (age, location, preferences)
* Delivery statistics and engagement patterns
* Custom field values and data quality metrics

**How to create:** Select any list or query result → Right-click → **[!UICONTROL Actions > Analyze]** → Choose analysis type (qualitative or quantitative) → Configure display options → Generate report.

**Sharing:** Export reports to Excel/PDF or save them to the **[!UICONTROL Reports]** folder for team access with appropriate permissions.

Learn more about [Descriptive analysis](../reporting/built-in-reports.md)

+++

+++ How can I design advanced reports on my data?

Campaign offers two approaches for creating advanced custom reports: technical reports in the client console for complex analysis, and visual dashboards for easier report building.

In the Client Console, you can:

* Build complex reports using SQL queries and custom calculations
* Create multi-page reports with charts, tables, and pivot tables
* Design conditional formatting and dynamic content
* Access the full Campaign data model and external databases (FDA)

Learn how to [Create custom reports (client console)](../reporting/custom-reports.md) 

+++

+++ What is a cube and how can I use it for reporting?

Cubes are multi-dimensional data structures that enable business users to explore and analyze Campaign data through pivot tables without technical skills. Think of them as pre-configured data models that simplify complex reporting.


* Technical users create and configure cubes defining dimensions (time, geography, channels) and measures (opens, clicks, revenue)
* Business users select a cube when creating reports and drag-and-drop dimensions to explore data
* Data is automatically aggregated and calculated based on cube configuration
* Results can be displayed as pivot tables, charts, or exported to Excel

Learn how to [Explore data with cubes](../reporting/gs-cubes.md)

+++

+++ Can I create a report from answers to an online survey?

Yes! Campaign includes a Survey module that allows you to create online questionnaires and generate built-in reports on survey responses.

**Important:** Survey management is not available in Campaign v8 Enterprise (FFDA) deployments. [Learn more](../architecture/enterprise-deployment.md).

**Survey capabilities:**

* Create online questionnaires with multiple pages and question types
* Collect responses in the database or local variables
* View real-time tracking of survey responses
* Generate dedicated reports on survey answers (breakdown by question, general statistics)
* Export survey responses to Excel, PDF, or CSV for further analysis
* Use survey data in targeting workflows to personalize campaigns

**Built-in survey reports:**

* **General report** - Response trends over time, distribution by origin and language
* **Breakdown of responses** - Detailed breakdown of answers for each question
* **Documentation report** - Visual representation of survey structure

**Advanced analysis:**

* Access survey responses from the **[!UICONTROL Responses]** tab and export data
* Use **[!UICONTROL Survey responses]** activity in workflows to target recipients based on their answers
* Combine survey data with other Campaign data for segmentation and personalization
* Create custom reports and cubes for multi-dimensional survey analysis

**Related topics:**

[Get started with surveys](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Survey reports](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ How can I share access to my reports?

Campaign provides flexible options for sharing reports with different user groups, controlling visibility and access permissions based on roles and responsibilities.

**Report access control:**

* **Folder permissions** - Place reports in folders with appropriate read/write access for user groups
* **Named rights** - Assign specific rights to view, create, or modify reports
* **Display context** - Define where reports appear: in **[!UICONTROL Reports]** folder, campaign tabs, or delivery screens
* **Web UI sharing** - Share dashboard links with team members through the Campaign Web UI

**How to configure access:**

1. Save your report to a specific folder in the client console
2. Configure folder access permissions for relevant operator groups
3. Define report properties: report type, display context, and availability
4. Test access with a user from the target group before broader rollout

**Best practice:** Create dedicated report folders for different teams (marketing, operations, management) with tailored access permissions. Document report purpose and refresh schedules.

**Related topics:**

[Custom reports](../reporting/custom-reports.md) | [User permissions](gs-permissions.md)

+++

+++ Can I export reports in different formats?

Yes, Campaign supports multiple export formats for both client console and Web UI reports, enabling easy sharing with stakeholders and integration with other tools.

**Available export formats:**

* **Excel (.xlsx)** - Best for data manipulation, further analysis, and pivot tables
* **PDF** - Ideal for presentations, executive summaries, and printed reports
* **CSV** - Perfect for data imports into other systems and BI tools
* **OpenDocument (.ods)** - Open-source spreadsheet format
* **XML** - For system integrations and automated processing

**How to export:**

* **Client console:** Open report → Click **[!UICONTROL Export]** button → Choose format → Save file
* **Web UI:** Open dashboard → Click export icon → Select format → Download
* **Automated exports:** Schedule regular exports using workflows with export activities

**Best practices:**

* Use Excel for reports requiring stakeholder analysis and annotations
* Use PDF for static reports sent to executives or archived for compliance
* Use CSV for integrations with data warehouses or external analytics tools
* Test exported reports to ensure formatting and data accuracy

**Related topics:**

[Custom reports](../reporting/custom-reports.md) | [Campaign Web UI reports](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Developers {#developers}

Access technical information for developers, including data model details, schemas, APIs, and customization capabilities.

+++ What is the Campaign data model?

Campaign's data model is a schema-driven relational database structure that defines how marketing data is organized and related. It consists of built-in tables for core marketing objects (recipients, deliveries, campaigns) and can be extended to meet your specific business needs.

**Key data model concepts:**

* **Schemas** - XML definitions describing table structure, fields, and relationships
* **Built-in tables** - Core marketing entities (recipients, deliveries, workflows, campaigns)
* **Links** - Relationships between tables (1-1, 1-N, N-N)
* **Enumerations** - Predefined value lists for dropdown fields
* **Extensions** - Custom fields and tables added to the standard model

**Main built-in schemas:**

* **Recipient (nms:recipient)** - Customer profiles and contact information
* **Delivery (nms:delivery)** - Email, SMS, and push campaigns
* **Workflow (xtk:workflow)** - Automation processes
* **Campaign (nms:operation)** - Marketing campaign orchestration
* **Tracking logs** - Opens, clicks, and engagement data

**Why it matters:** Understanding the data model is essential for creating workflows, building queries, extending schemas, and developing custom integrations. The schema-based approach ensures data consistency and enables powerful querying capabilities.

**Related topics:**

[Campaign data model](../dev/datamodel.md) | [Data model best practices](../dev/datamodel-best-practices.md)

+++

+++ How to work with Campaign schemas?

Schemas are the foundation of Campaign's data structure, defining tables, fields, and relationships in XML format. Understanding schemas is crucial for customization, integration, and advanced workflow development.

**What schemas define:**

* **Table structure** - Database tables and their corresponding application objects
* **Field properties** - Data types, labels, validation rules, and default values
* **Relationships** - Links between tables (joins) and cardinality
* **Indexes** - Database optimization for query performance
* **Access control** - Which fields users can view and modify

**Working with schemas:**

* **View schemas:** Access via **[!UICONTROL Administration > Configuration > Data schemas]** in the client console
* **Extend schemas:** Create extension schemas (e.g., `cus:recipient` extends `nms:recipient`) to add custom fields without modifying core schemas
* **Create custom schemas:** Build entirely new tables for business-specific data
* **Update database:** Apply schema changes using **[!UICONTROL Tools > Advanced > Update database structure]**

**Common use cases:**

* Adding custom fields to recipient table (company ID, loyalty tier, preferences)
* Creating custom tables for products, stores, or transactions
* Defining relationships between custom and built-in tables
* Implementing business-specific data models

**Important:** Never modify built-in schemas directly. Always use extension schemas to preserve upgrade compatibility and Adobe support.

**Related topics:**

[Get started with schemas](../dev/schemas.md) | [Extend a schema](../dev/extend-schema.md)

+++

+++ How to use a custom recipient table?

Campaign allows you to use a custom table instead of the built-in recipient table when your business requires a different data structure for targeting (e.g., B2B accounts, subscribers, leads, or external contacts).

**Why use a custom recipient table:**

* Target B2B companies or organizational units instead of individual contacts
* Separate subscriber data from main customer database
* Use an existing customer table from another system
* Implement multi-brand architectures with separate contact tables
* Comply with specific data governance requirements

**Implementation steps:**

1. Create your custom schema defining the recipient table structure
2. Include mandatory fields (email, primary key, exclusion flags)
3. Configure target mappings to link your table with deliveries
4. Update delivery templates to use the new target mapping
5. Adapt workflows and queries to reference the custom table

**Key considerations:**

* Custom recipient tables must include required fields for deliveries (email, exclusions, tracking)
* Workflows and forms need adaptation to work with the custom structure
* Some built-in features may require customization
* Testing is critical before migrating production campaigns

**Best practice:** Start with extending the standard recipient table before considering a custom table. Custom recipient tables add complexity and should only be used when truly necessary.

**Related topics:**

[Custom recipient table](../dev/custom-recipient.md) | [Target mappings](../audiences/target-mappings.md)

+++

+++ What are the best practices to define queries in Campaign?

Campaign's query editor is a powerful visual tool for building database queries without SQL knowledge. Mastering it is essential for effective targeting, segmentation, and data analysis.

**Where queries are used:**

* **Workflow activities** - Query, Split, Update data, Enrichment activities
* **Delivery targeting** - Define recipient populations for campaigns
* **Lists** - Create dynamic or static recipient lists
* **Reports** - Build custom data extractions and analysis
* **Filters** - Create reusable targeting criteria

**Query best practices:**

* **Start simple** - Build queries incrementally, testing at each step
* **Use filtering dimensions** - Leverage relationships between tables (recipients → deliveries → tracking logs)
* **Optimize performance** - Index frequently queried fields, avoid complex calculated fields
* **Leverage predefined filters** - Reuse and combine existing filters for consistency
* **Test with small samples** - Validate query logic before running on full database
* **Document complex queries** - Add descriptions for maintenance and knowledge transfer

**Common query patterns:**

* Target recipients who opened specific delivery: Filter on tracking logs linked to recipients
* Find inactive contacts: Query on last delivery date or tracking activity
* Segment by behavior: Combine delivery, tracking, and profile criteria
* Exclude previous recipients: Use set operations (union, intersection, exclusion)

**Access generic query editor:** **[!UICONTROL Tools > Generic query editor]** for ad-hoc database exploration and data extraction outside workflows.

**Related topics:**

[Query editor](../start/query-editor.md) | [Query activity in workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ How can I import a data package?

Data packages enable you to export and import Campaign configurations (schemas, workflows, typologies, filters) and data between instances. This is essential for deploying configurations from development to production or sharing components across organizations.

**What can be packaged:**

* **Configuration objects** - Schemas, workflows, typology rules, forms, filters
* **Campaign components** - Delivery templates, campaign templates, content blocks
* **Application settings** - Operators, operator groups, folder structures
* **Data** - Recipient lists, seed addresses, content fragments
* **Custom developments** - JavaScript code, SQL scripts, web applications


**Package types:**

* **User package** - Custom configurations you create and export
* **Platform package** - Adobe-provided features and updates
* **Data package** - Contains actual data records, not just structure

**Best practices:**

* Always export packages from the same or older Campaign version
* Test package imports in development environment before production
* Document package contents and dependencies
* Use version control for package XML files
* Back up instance before major package imports

Learn more about how to [Work with data packages](../dev/packages.md)

+++

+++ Where can I find the list of Campaign v8 APIs?

Campaign v8 provides comprehensive API documentation covering both SOAP APIs (for client console interactions) and REST APIs (for modern integrations). The API reference includes all available methods, parameters, and response formats.

**Campaign API types:**

* **SOAP APIs** - Traditional APIs for Campaign client console operations, schema manipulation, and workflow control
* **REST APIs** - Modern HTTP APIs for external system integrations, profile management, and event triggering
* **JavaScript APIs** - Server-side scripting APIs for workflow activities and custom business logic

**API documentation resources:**

* **Full API reference:** Comprehensive SOAP API documentation with method signatures, parameters, and examples
* **REST API guide:** Modern REST endpoints for profiles, events, and organizational units
* **JavaScript API:** Server-side functions available in workflow scripts and web applications

**Common API use cases:**

* Integrate Campaign with CRM, ERP, or custom applications
* Automate campaign operations and workflow execution
* Synchronize data between systems in real-time
* Build custom monitoring and alerting solutions
* Create external interfaces for Campaign data and operations

**Access:** [Campaign v8 API documentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html){target="_blank"}

+++


+++ How do I monitor workflows from API?

Campaign APIs allow you to programmatically control and monitor workflow execution, enabling external monitoring systems, automated alerting, and custom orchestration solutions.

**What you can do via API:**

* **Start workflows** - Trigger workflow execution programmatically
* **Pause/Resume workflows** - Control workflow execution flow
* **Stop workflows** - Terminate running workflows
* **Query workflow status** - Check if workflows are running, paused, or completed
* **Retrieve logs** - Access workflow execution logs and error messages
* **Monitor activity progress** - Track individual workflow activity completion

**API endpoint:**

All workflow control commands use the same POST endpoint with different method parameters:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Available commands:**

* `{"method":"start"}` - Start a workflow
* `{"method":"pause"}` - Pause a running workflow
* `{"method":"resume"}` - Resume a paused workflow
* `{"method":"stop"}` - Stop a workflow

**Common use cases:**

* Build custom monitoring dashboards showing workflow health
* Implement automated alerting when workflows fail or run too long
* Orchestrate workflows from external schedulers or event systems
* Create workflow dependencies across multiple Campaign instances
* Generate custom workflow execution reports

**Best practice:** Combine API monitoring with workflow audit trail for comprehensive workflow governance. Use external monitoring tools to track workflow SLAs and performance metrics.

Learn how to [Control workflows via API](../dev/api/controlling-a-workflow.md)

+++

+++ How can I update the database structure?

After modifying Campaign schemas (adding fields, creating tables, changing data types), you must update the physical database structure to apply your changes. This synchronization ensures the database matches your schema definitions.

**When database updates are needed:**

* Adding new fields to existing schemas
* Creating custom tables or extending built-in tables
* Modifying field properties (data type, length, required status)
* Adding or removing links between tables
* Creating new indexes for query optimization


**Important considerations:**

* **Backup first** - Always back up your database before structural changes
* **Test in development** - Validate schema changes in dev environment before production
* **Downtime planning** - Large structural changes may require brief maintenance windows
* **For Managed Cloud Services** - Coordinate major changes with Adobe support
* **Reversibility** - Some changes (like removing fields) may cause data loss

**Best practice:** Use schema versioning and change tracking. Document all custom schema modifications for maintenance and troubleshooting.

**Related topics:**

[Update database structure](../dev/update-database-structure.md) | [Extend schema](../dev/extend-schema.md)

+++

## Privacy {#privacy}

Understand how Adobe Campaign helps you comply with privacy regulations like GDPR and CCPA, and manage data subject requests.

+++ What are the key privacy concepts in Campaign?

Campaign helps you comply with privacy regulations (GDPR, CCPA, PDPA, LGPD) through tools for managing data subject rights, consent, and data retention. Key concepts include privacy regulations, personal data identification, data subject rights (access, deletion, portability), consent management, and data retention policies.

As Data Controller, you're responsible for handling data subject requests, maintaining consent records, and ensuring transparent data use.

Learn more about [Privacy management](../start/privacy.md)

+++

+++ How do I ensure privacy compliance in Campaign?

Campaign provides tools for privacy compliance, but legal responsibility rests with you. Work with legal counsel for your privacy program.

**Essential actions:**

* Establish processes for handling data subject requests (access, deletion)
* Implement consent management with timestamps and scope tracking
* Include unsubscribe links in all marketing emails
* Audit data sources and remove unused data
* Apply least-privilege access controls

Campaign offers Privacy Core Service integration, consent tracking, automated deletion workflows, and audit trails for compliance.

Learn more about [Privacy management](../start/privacy.md)

+++

+++ How do I collect and manage user consent in Campaign?

Valid consent requires active, specific, informed, and revocable agreement. Users must take explicit action—no pre-checked boxes or silence as consent. Separate consents for different purposes (unbundled), provide clear explanations, and maintain records with timestamps.

**Best practices:** Provide granular opt-in options, periodically refresh consent, make preference centers easy to access, and frame consent as building trust.

**Technical implementation in Campaign:**

Campaign provides subscription services, preference centers, opt-out flags, and custom consent fields for tracking consent.

* Extend recipient schema for consent fields (date, type, source)
* Create subscription services for each consent type
* Build preference center web forms
* Use workflows to enforce consent in targeting
* Maintain audit trails

Consult legal counsel to ensure your implementation meets regulatory requirements.

**Related topics:**

[Subscription services](../start/subscriptions.md) | [Privacy and consent](../start/privacy.md#consent-retention-roles) | [Privacy management](../start/privacy.md)

+++

+++ What data is deleted when I process a deletion request?

Campaign automatically deletes all data linked to a data subject: recipient profile, delivery and tracking logs, custom data with ownership relationships, subscription history, and web tracking data.

**How it works:** Campaign deletes all data where the link to the recipient has `integrity="own"` in the schema definition, ensuring cascading deletion across related tables.

You can customize deletion scope by modifying link integrity in schemas, but consult legal counsel first. Deletion is permanent and cannot be undone.

**Related topics:**

[Privacy management](../start/privacy.md) | [Schema links](../dev/schemas.md)

+++

+++ Do privacy deletions affect my delivery reports?

No. Campaign reports are based on pre-calculated aggregated metrics (total sent, opens, clicks), not live queries on individual logs. Deleting individual recipient data doesn't change historical aggregate statistics.

Overall delivery statistics and performance metrics remain intact, while individual tracking logs and personal details are removed. This allows you to maintain marketing analytics while respecting data subject rights.

**Related topics:**

[Privacy management](../start/privacy.md) | [Reports](../reporting/gs-reporting.md)

+++

+++ How do I prevent re-importing deleted data?

You must delete data from all source systems, not just Campaign. Data often flows from external systems (CRM, e-commerce, data warehouses).

**Required actions:** Identify all data sources, delete from source systems, add to exclusion/suppression lists, update import workflows to respect deletion flags, and document the process.

As Data Controller, you're responsible for complete data removal across your entire technology ecosystem.

**Related topics:**

[Privacy management](../start/privacy.md) | [Import workflows](../config/workflows.md)

+++

+++ Can deleted users opt in again?

Yes. Data subjects can opt in again after deletion. Campaign creates a completely new recipient record with no link to previous deleted data—the profile starts with a clean slate.

Campaign's audit trail records both the deletion event and new profile creation, demonstrating compliance and showing the new opt-in was freely given after deletion.

**Related topics:**

[Privacy management](../start/privacy.md) | [Subscriptions](../start/subscriptions.md)

+++

## Still need help? {#get-help}

Can't find what you're looking for? Here are additional resources to help you succeed with Adobe Campaign v8.

### Community Support

Connect with other Campaign users and Adobe experts to share knowledge and get answers.

* **[Adobe Campaign Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}** - Ask questions, share solutions, and connect with the Campaign community
* **[Experience League Forums](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - Browse discussions across all Adobe products
* **[Campaign Community Office Hours](https://experienceleague.adobe.com/){target="_blank"}** - Join live sessions with Adobe experts

### Documentation & Learning

Access comprehensive guides, tutorials, and training materials.

* **[Campaign Tutorials](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"}** - Step-by-step video guides and hands-on tutorials
* **[What's New](whats-new.md)** - Latest features and capabilities
* **[Release Notes](release-notes.md)** - Current and previous release information
* **[Versions and Upgrades](upgrades.md)** - Learn about Campaign versions, upgrades, and how to check your version

### Technical Resources

Find detailed technical documentation and developer resources.

* **[Campaign APIs](https://experienceleague.adobe.com/developer/campaign-api/api/index.html){target="_blank"}** - Complete API reference documentation
* **[Compatibility Matrix](compatibility-matrix.md)** - Supported systems and versions
* **[Versions and Upgrades FAQ](upgrades.md#upgrades-faq)** - Check your version and learn about upgrades

### Support & Services

Get help from Adobe's support team and manage your instance.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Log support cases and manage users
* **[Adobe Customer Care](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contact the support team
* **[Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html){target="_blank"}** - Manage your Campaign instance settings
* **[System Status](https://status.adobe.com/){target="_blank"}** - Check Adobe services status

### Training & Certification

Advance your skills with official Adobe training and certification programs.

* **[Experience League Help](https://experienceleague.adobe.com/en/browse/campaign/campaign-v8){target="_blank"}** - Help resources for Campaign v8 (Web UI and CLient console)
* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Official instructor-led and self-paced courses
* **[Adobe Campaign Certification](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Validate your expertise with professional certification
* **[Experience League Learning Paths](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - Guided learning journeys

### Other Helpful Resources

* **[Campaign Classic v7 Documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html){target="_blank"}** - Reference for Classic v7 users
* **[Campaign Web UI Documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - New web interface guide
* **[Deliverability Best Practices](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}** - Optimize email delivery

