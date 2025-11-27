---
title: Campaign v8 Frequently Asked Questions
description: Get answers to common Adobe Campaign v8 questions about setup, configuration, messaging, workflows, and more
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, answers, help, support, troubleshooting
hide: yes
hidefromtoc: yes
---
# Frequently Asked Questions {#faq}

Get quick answers to the most common questions about Adobe Campaign v8. Whether you're just getting started or looking for advanced configuration help, you'll find answers organized by topic below.

**New to Campaign?** Start with [General Questions](#general) and [Key Concepts](#key-concepts).  
**Need technical help?** Check [Developers](#developers) and [Campaign Settings](#settings).  
**Can't find your answer?** Visit our [Community Forums](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} or [contact support](#get-help).

>[!TIP]
>
>Use Ctrl+F (Cmd+F on Mac) to search for specific keywords on this page. Click any question to expand the answer.


## General Questions {#general}

Get answers to the most common questions about Adobe Campaign v8, including how to connect, upgrade, and get support.

+++ How can I connect to Campaign v8?

You need to download and install Campaign client console to connect to Adobe Campaign.
    
[Click here to learn more](connect.md).

Starting Campaign v8.6 release, you have access to the **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. 

Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui).

Learn more in the [Adobe Campaign Web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

>[!TIP]
>
>**Troubleshooting connection issues:**
>
>* Verify your Adobe ID credentials are correct
>* Ensure your client console version matches the server version
>* Check network connectivity and firewall settings
>* Clear client console cache if experiencing issues
>* Contact your administrator to verify your user permissions

**Related topics:**

* [Install the client console](connect.md)
* [Campaign user interface](campaign-ui.md)
* [User permissions](gs-permissions.md)

+++

+++ Can Campaign v8 be installed on an on-premise or hybrid environment?

Campaign v8 is only available in Managed Cloud Services, fully hosted by Adobe.

+++

+++ How can I upgrade Campaign to the latest version?

Adobe Campaign is regularly updated. Minor versions are released every year with new features, improvements and fixes. In addition, we periodically release builds with cumulative fixes only.

This regular frequency of updates aims at getting the latest and greatest in your hands, keeping your environment secure and improving your experience with our product. This is the reason why we believe it is critical that you run the most recent version of Adobe Campaign. 

>[!NOTE]
>
>As a Managed Cloud Services user, your instance is upgraded by Adobe with new releases.

+++

+++ How to improve email deliverability?

Email deliverability, a critical component to every sender's marketing program success, is characterized by ever-changing criteria and rules. Effectively navigating in this digital world requires regular tuning of your email strategy, with consideration to key deliverability trends, to best reach your audiences.

Refer to this guide to learn [Deliverability Best Practices](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}

Learn how to implement deliverability in Campaign [in this guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html){target="_blank"}

>[!TIP]
>
>**Key deliverability tips:**
>
>* Maintain a clean email list and remove inactive subscribers regularly
>* Use double opt-in to ensure engaged recipients
>* Monitor your sender reputation and IP reputation
>* Authenticate your emails with SPF, DKIM, and DMARC
>* Respect unsubscribe requests immediately
>* Test your emails before sending to large audiences

**Related topics:**

* [About deliverability](../send/about-deliverability.md)
* [Control message content](../send/control-message-content.md)
* [Monitor deliverability](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ How can I make sure my delivery is sent without errors?

Adobe Campaign comes with a set of dashboards and tools to monitor your email deliveries.

[Read out Campaign Classic v7 documentation to learn](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html){target="_blank"} how to make sure your messages are being sent, monitor the execution and engage action if an error occurs.

+++

+++ Can I monitor workflow execution?

Understand how to monitor Campaign workflow execution [this page](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}

+++

+++ Which systems and components Campaign v8 is compatible with?

You can get the list of all systems and components supported for the latest build of Campaign in [Adobe Campaign Compatibility matrix](compatibility-matrix.md).

+++

+++ How can I download Campaign?

You can get the installation program and the client console from Adobe Download Center.
    
As an Admin user, access Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} to download Adobe Campaign.
    
Learn more about the Distribution Center [on this page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

+++

+++ How can I log an issue?

Creating a case allows you to contact the Adobe Customer Support Team about any issues that you face with your Adobe products. To help resolve or troubleshoot your issues, the Adobe Admin Console will allow you to chat with Adobe Customer Support.

To log an issue or start a chat session in that new system, connect to [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}. 

This system requires individual accounts for each user, with correct permissions. If you find that you can't log in with your Adobe ID, request access via the Experience League, and the Customer Care team will get you set up as soon as possible. [Learn more](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Join Campaign Community: search for answers in existing question or ask the experts. [Join the conversation](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"}

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

+++ What is my version of Campaign?

Check your [version and build number](connect.md#ac-version) from the **Help > About...** menu of Campaign client console.

+++

+++ What are the differences between Campaign Classic v7 and Campaign v8?

Campaign v8 is the next-generation version of Campaign, designed for Managed Cloud Services. It brings significant improvements in infrastructure, security, deliverability, and monitoring.

Adobe Campaign v8 is exclusively available as a **Managed Cloud Service**, and cannot be deployed on an on-premise or hybrid environment.

[Learn more about the transition from Campaign Classic v7 to v8](v7-to-v8.md).

+++

+++ How can I set up user permissions?

As a Campaign administrator, you can set up permissions for users of your organization.

These are a set of rights and restrictions that authorize or deny to:

* Access to certain functionalities
* Access to certain data
* Create, modify and/or delete data

[Learn more](../start/gs-permissions.md) about user permissions in Campaign v8.

**Related topics:**

* [Get started with permissions](gs-permissions.md)
* [Manage user permissions](manage-permissions.md)
* [Add permissions on folders](folder-permissions.md)

+++

+++ How to ensure Privacy compliance with Campaign?

Adobe Campaign offers a set of tools to help you with your Privacy Compliance for GDPR, CCPA and other privacy regulations.

[Learn more](../start/privacy.md) about privacy management and the tools and functionalities that Adobe Campaign provides to help you with your privacy compliance. 

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

* [Get started with workflows](config/workflows.md)
* [Build your first workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}
* [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Monitor workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

* [Create your first delivery](create-message.md) - Step-by-step guide
* [Work with delivery templates](../send/create-templates.md) - Save time with templates
* [Delivery best practices](delivery-best-practices.md) - Recommendations for success
* [Define the email content](../send/defining-the-email-content.md) - Content creation options
* [Preview and proofs](../send/preview-and-proof.md) - Test before sending
* [Configure and send](../send/configure-and-send.md) - Final steps to send
* [Personalize content](../send/personalize.md) - Add dynamic personalization

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

* [Get started with SMS](../send/sms/sms.md) - Complete SMS guide
* [SMS delivery settings](../send/sms/sms-delivery-settings.md) - Configuration options
* [SMPP external account settings](../send/sms/smpp-external-account.md) - Provider setup
* [Create a SMS delivery](../send/sms/create-sms.md) - Step-by-step creation
* [SMS content](../send/sms/sms-content.md) - Content design guidelines
* [Send SMS proofs](../send/sms/sms-proofs.md) - Testing SMS
* [Monitor SMS](../send/sms/sms-monitor.md) - Track and analyze deliveries

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

* [Create and send push notifications](../send/push.md) - Complete push guide
* [Configure push notification channel](../send/push-settings.md) - Channel setup
* [Design an Android rich push](../send/rich-push-android.md) - Android rich notifications
* [Design an iOS rich push](../send/rich-push-ios.md) - iOS rich notifications  
* [Configure with Data Collection](../send/push-data-collection.md) - Modern revised integration method
* [Track and monitor](tracking.md) - Analyze push performance

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

* [Track and monitor messages](tracking.md)
* [Delivery reports](../reporting/delivery-reports.md)
* [Understand delivery failures](../send/delivery-failures.md)
* [Configure tracked links](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (Campaign Classic v7 documentation)

+++

+++ How to translate an error message?

An error message is displayed in a foreign language? All error messages and their translation are listed in [this page](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html){target="_blank"}.

+++

+++ Can I create a webform and collect answers in Campaign?

Yes. Create web forms using **Campaign Web Applications & Forms** (client console) for full control over form logic and validation, or use **Campaign Landing Pages** (Web UI) with a modern drag-and-drop interface for subscriptions and lead generation. Both collect data directly into Campaign and integrate with workflows for automated actions.

[Learn more about web applications and forms](../dev/webapps.md) | [Campaign Web UI landing pages](https://experienceleague.adobe.com/en/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 vs Previous Versions {#v7-differences}

Understand the key differences between Campaign v8 and previous versions (Classic v7 and Standard), including architecture, deployment, migration paths, and feature changes.

+++ What are the main differences between Campaign v8 and previous versions?

Campaign v8 is a complete reimagining of Adobe Campaign, designed for modern cloud-native architecture and bringing significant improvements over Campaign Classic v7 and Campaign Standard:

**Deployment Model:**

* **v8:** Managed Cloud Services only - fully hosted and managed by Adobe
* **v7/Standard:** On-premise, hybrid, or hosted options available
* **Benefit:** Zero infrastructure management, automatic scaling, enterprise-grade security

**Architecture & Performance:**

* **v8:** Enhanced Full FDA (FFDA) architecture with PostgreSQL database
* **v8:** Optimized for handling millions of profiles and high-volume sending
* **v8:** Significantly improved query performance and data processing speed
* **Benefit:** Better performance for large-scale operations and complex campaigns

**User Interface:**

* **v8:** New Campaign Web user interface alongside client console
* **v8:** Modern, responsive design with improved user experience
* **v8:** Simplified campaign creation and management workflows
* **Benefit:** Faster onboarding, easier campaign execution, better accessibility

**Upgrades & Maintenance:**

* **v8:** Automatic upgrades managed by Adobe - always on latest stable version
* **v7:** Manual upgrade planning and execution required
* **Benefit:** Reduced maintenance burden, immediate access to new features, no downtime

**APIs & Integration:**

* **v8:** Modern REST APIs with enhanced performance and reliability
* **v8:** Seamless integration with Adobe Experience Cloud solutions
* **Benefit:** Easier integrations, better interoperability, modern development practices

[Learn more about Campaign v8 key capabilities](whats-new.md)

**Related topics:**

* [From Campaign Classic v7 to v8](v7-to-v8.md)
* [From Campaign Standard to v8](acs-to-v8.md)
* [Campaign v8 architecture](../architecture/architecture.md)
* [Guardrails and limitations](ac-guardrails.md)

+++

+++ Should I migrate from Campaign Classic v7 or Campaign Standard to v8?

**Campaign v8 is ideal for organizations that need:**

* **High-volume campaigns** - Send millions of messages with improved performance and reliability
* **Enterprise scalability** - Grow your database and campaigns without performance concerns
* **Modern web user interface** - Intuitive, responsive Campaign Web UI for faster campaign creation and improved user experience
* **Cloud-native benefits** - Leverage automatic updates, managed infrastructure, and elastic scaling
* **Long-term support** - Campaign v8 is Adobe's strategic platform with extended support, while previous versions will reach End of Support in the coming years
* **Reduced IT overhead** - Eliminate infrastructure management and upgrade planning

**When to consider migrating:**

* Your current Campaign instance handles large data volumes (millions of profiles)
* You're experiencing performance issues with complex workflows or targeting
* You want to reduce infrastructure management and maintenance costs
* You need seamless integration with other Adobe Experience Cloud solutions
* You're planning a major upgrade or infrastructure refresh anyway
* **You want future-proof technology** - Campaign Classic v7 and Campaign Standard will reach End of Support, making v8 the strategic long-term solution
* **Your team needs a modern interface** - The new Campaign Web UI offers a more intuitive, accessible experience for marketers

**Migration considerations:**

* Automated migration is not yet available - Adobe provides migration support and guidance
* v8 is Managed Cloud Service only (no on-premise or hybrid deployment)
* Some technical implementations may differ from v7 - review the [compatibility matrix](compatibility-matrix.md)
* Data migration and testing require planning and resources

**Next steps:**
Contact your Adobe representative to:

* Assess your migration readiness and timeline
* Understand the specific benefits for your use case
* Plan the migration strategy and resource allocation
* Access migration tools and support

**Related topics:**

* [From Campaign Classic v7 to v8](v7-to-v8.md) - Detailed comparison and migration guide for v7 users
* [From Campaign Standard to v8](acs-to-v8.md) - Migration path for Standard users
* [Campaign v8 capability matrix](../start/compatibility-matrix.md)

+++

+++ What Campaign Classic v7 features are different or unavailable in v8?

Campaign v8 brings most Campaign Classic v7 capabilities with enhancements, but some features have changes due to the cloud-native architecture:

**Not available in v8:**

* **On-premise and hybrid deployments** - v8 is Managed Cloud Services only
* **Direct database access** - Use provided APIs and tools instead
* **Customer-managed infrastructure** - Adobe manages all infrastructure

**Different implementations in v8:**

* **Technical workflows** - Some optimized for cloud architecture, may work differently
* **Database structure** - Enhanced FFDA architecture may require schema adaptations
* **Custom integrations** - May need updates for cloud-based architecture
* **Low-level customizations** - Some require different approaches in managed environment

**Enhanced or replaced in v8:**

* **Build upgrades** - Now automatic (Adobe managed) instead of manual
* **Performance tuning** - Handled by Adobe infrastructure optimization
* **Security patches** - Applied automatically by Adobe
* **Backup and recovery** - Managed by Adobe as part of service


**Important:** Most marketing and operational features are available and improved in v8. Technical and infrastructure-level features are managed by Adobe in the cloud environment.

[Review the complete compatibility matrix](compatibility-matrix.md) for detailed information.

**Related topics:**

* [Guardrails](ac-guardrails.md)
* [v7 to v8 transition guide](v7-to-v8.md)

+++

## Profiles and Audiences {#audiences}

Find answers to questions about managing profiles, creating audiences, importing data, and targeting recipients for your campaigns.

+++ How to create recipients?

Create recipients manually in the client console for individual profiles, import from files (CSV/TXT) for bulk additions, use web forms for self-registration, or integrate via APIs from external systems. Use import workflows for recurring data loads.

[Create profiles manually](../audiences/create-profiles.md) | [Import profiles from a file](../audiences/import-profiles.md) | [Collect profiles with web forms](../audiences/collect-profiles.md)

+++

+++ How to import profiles?

Campaign provides multiple import methods: simple file import using the import wizard, workflow-based import for complex transformations, recurring imports with scheduled workflows from SFTP, and API import for programmatic integration.

For file imports, prepare your data file (CSV/TXT, UTF-8 encoding), use the import wizard or workflow, map columns to Campaign fields, define update/insert rules, and test with a small sample first. Use workflows for recurring imports and apply deduplication rules.

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

>[!TIP]
>
>Use workflows for lists requiring regular updates, and manual creation for one-time segmentation.

[Create audiences](../audiences/create-audiences.md) | [List update activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ How can I deduplicate a population before sending a message?

Use the **[!UICONTROL Deduplication]** activity in a workflow to remove duplicate recipients before delivery. Place it between your **[!UICONTROL Query]** and **[!UICONTROL Delivery]** activities, then choose your deduplication criteria (typically email address or recipient ID) and which record to keep.

>[!TIP]
>
>Always deduplicate before sending to ensure each person receives your message only once.

[Deduplication activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"}

+++

+++ How to identify and target subscribers to a newsletter?

Campaign automatically tracks newsletter subscriptions through information services. To target subscribers:

* Use a **[!UICONTROL Query]** activity and filter on **[!UICONTROL Subscriptions]** > select your newsletter service
* Target subscribers directly from your delivery by choosing **[!UICONTROL To > Subscribers of an information service]**
* Build subscriber lists with the **[!UICONTROL Subscription Services]** workflow activity

Campaign tracks subscription/unsubscription history and manages opt-in/opt-out automatically.

[Manage subscriptions](../start/subscriptions.md) | [Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ What is the best practice to exclude profiles from a target population?

Use the **[!UICONTROL Exclusion]** activity in a workflow to remove unwanted profiles from your target. Place it after your targeting activities and define which population to exclude.

[Exclusion activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

+++

+++ Can I use external profiles without importing them in Campaign?

Yes, Campaign v8 allows you to work with external profiles stored in an external database without loading them into Adobe Campaign. [Learn more](../audiences/external-profiles.md).

+++

+++ How do I create test profiles for my deliveries?

Test profiles are special recipients used to send proofs and validate deliveries without impacting your production database. Create them in **[!UICONTROL Profiles and Targets > Test profiles]**, or use the **[!UICONTROL Seed addresses]** feature to automatically add test recipients to your deliveries for quality assurance and inbox monitoring.

[Test profiles](../audiences/test-profiles.md)

+++

## Message Design {#design}

Learn how to design effective marketing messages in Campaign v8, including email templates, personalization techniques, and multilingual content. Design your messages in the client console or use the modern **Email Designer** in the Campaign Web UI for an enhanced visual editing experience.

+++ What are the best practices for designing emails in Campaign?

Key guidelines: ensure mobile-responsive design, use HTML 4.0/XHTML compatible code with inline CSS, optimize images (under 100KB) with alt text, use personalization merge fields, test across email clients before sending, and include a plain text version. Aim for total email size under 500KB for optimal deliverability.

[Email design guide](../send/email.md) | [Delivery best practices](delivery-best-practices.md)

+++

+++ What is a delivery template?

A delivery template is a pre-configured delivery that saves all settings and parameters for reuse across multiple campaigns. Templates include target rules, content design, personalization, technical settings (sender, reply-to), and typology rules. Create once and reuse to maintain consistency and speed up campaign creation.

[Create delivery templates](../send/create-templates.md)

+++

+++ Can I easily import an existing HTML to create an email in Campaign?

Yes. Import HTML content via direct copy/paste into the content editor, file upload from your computer, or load from a URL. Ensure your HTML uses email-compatible code (HTML 4.0/XHTML) with inline CSS, and host images on a public server. Campaign automatically adds personalization and tracking to imported HTML.

>[!TIP]
>
>For the best email design experience, use the **Email Designer** in the Campaign Web UI, which offers modern drag-and-drop capabilities and built-in responsive templates, rather than importing raw HTML.

[Import HTML content](../send/defining-the-email-content.md)

+++

+++ How can I create a subscription-based newsletter in Campaign?

Yes. Use Campaign's information services to manage newsletter subscriptions. Key capabilities include automatic opt-in/opt-out handling, subscription tracking, compliance management (GDPR, CAN-SPAM), multi-newsletter support, web integration for sign-up forms, and targeted delivery to subscribers.

[Manage subscriptions](../start/subscriptions.md)

+++

+++ How can I personalize messages?

Campaign offers personalization capabilities to create relevant, targeted messages based on recipient data, behavior, and preferences.

**Personalization options:**

* **Personalization fields** - Insert recipient data (e.g., `"Hello {{firstName}}")`
* **Personalization blocks** - Use predefined or custom content blocks
* **Conditional content** - Display different content based on recipient criteria
* **Behavioral data** - Leverage browsing history, purchase patterns, or engagement metrics

Test personalization before sending to verify merge fields and conditional logic work correctly.

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

[Web application localization](../dev/webapps.md)

+++

+++ Can I use AI-powered content in my emails?

Yes, but **only through the Campaign Web UI**. AI Assistant, powered by Microsoft Azure OpenAI and Adobe Firefly, helps create professional, brand-consistent content across email, SMS, and push notifications.

**Key capabilities:**

* Generate text (email copy, subject lines, SMS/push content) and brand-aligned images
* Create content variations optimized for different audiences
* Refine content (elaborate, summarize, rephrase, simplify)
* Upload brand assets and get brand alignment scoring
* Use existing content as reference and upload style reference images

>[!NOTE]
>
>AI Assistant is available exclusively in the Campaign Web UI and currently supports English only. Users need proper permissions and must agree to a user agreement.

[AI Assistant overview](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI Assistant use cases](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Brand alignment](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Testing and Sending Messages {#send}

Learn best practices for testing, validating, sending, and tracking your marketing messages to ensure successful campaign delivery.

+++ What is the delivery analysis?

Delivery analysis is a validation phase Campaign runs before sending. It calculates the target population, validates content, checks for errors, applies typology rules, and estimates delivery volume.

Campaign generates logs showing warnings and errors. Errors block delivery and must be fixed; warnings are advisory. Always review analysis logs before sending.

[Delivery analysis guide](../send/delivery-analysis.md)

+++

+++ Why should I create proofs?

Proofs are test messages that validate your delivery before sending to your main audience. Use proofs to verify personalization, test content rendering across email clients, confirm links and tracking work, check images and attachments, and validate mobile responsiveness.

Proofs help catch errors before they reach thousands of recipients, enable stakeholder approval, and test inbox placement. Send proofs to multiple email clients and devices, and always obtain approval before production sends.

[Proofs and preview guide](../send/preview-and-proof.md)

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

[Configure wave sending](../send/configure-and-send.md#sending-using-multiple-waves)

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


>[!TIP]
>
>Use the Campaign Web UI for faster, more intuitive email creation with modern design tools. Use the client console for complex targeting or advanced workflow-based campaigns.

[Create your first email](create-message.md) | [Email design guide](../send/email.md)

+++

+++ How to schedule a delivery?

Campaign allows you to schedule deliveries for future sending to optimize send times and coordinate campaigns.

**Scheduling options:**

* **Delivery properties** - Send immediately, schedule for specific date/time, or defer by hours/days
* **Campaign level** - Coordinate all deliveries within a campaign
* **Workflow Scheduler activity** - For recurring deliveries, complex patterns, and event-triggered campaigns

Campaign also supports contact date optimization (best send time per recipient) and time zone adaptation (same local time for all recipients).

[Schedule delivery sending](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Can I add an attachment to emails?

Yes. Campaign supports static attachments (same file for all recipients) and personalized attachments (different files per recipient based on profile data). Add attachments in the **[!UICONTROL Attachments]** section of your delivery properties.

**Important considerations:**

* Keep attachments under 1MB for optimal deliverability
* Attachments can trigger spam filters; test thoroughly before sending
* Avoid file types commonly blocked by email clients (.exe, .zip, .js)
* For large files, consider using tracked download links instead

Use safe file formats (PDF, JPEG, PNG, DOCX) and test with seed addresses before production sends.

[Email attachments guide](../send/email.md#attachments)

+++

+++ How can I configure tracked links in an email delivery?

Campaign automatically converts all URLs in your email into tracked links to monitor recipient engagement. Access the **[!UICONTROL Tracking]** section in your delivery to configure tracking settings for each link.

**Configuration options:**

* **Enable/disable tracking** - Control tracking per link
* **Link labels** - Add descriptive names for reporting (e.g., "Shop Now CTA")
* **Link categories** - Group links by type for aggregated analysis
* **Tracking type** - Track clicks, opens, or both

Campaign tracks content links, mirror page links, unsubscribe links, and can include an optional tracking pixel for email opens. Use meaningful labels and categories to simplify reporting and quickly identify high-performing content.

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

>[!TIP]
>
>Monitor your quarantine list regularly. Increasing quarantine rates often signal data quality issues that need attention before they impact sender reputation.

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

* [Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}
* [Workflow activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

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

* [Import best practices](../start/import.md)
* [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [Recurring import workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ Can I monitor workflow execution?

Yes. Campaign provides comprehensive workflow monitoring capabilities to track execution, identify issues, and optimize performance.

**Monitoring options:**

* **Workflow dashboard** - View real-time execution status, progress, and activity states
* **Execution logs** - Access detailed logs for each activity and transition
* **Audit trail** - Track workflow modifications and execution history
* **Alerts and notifications** - Set up email alerts for failures or specific conditions

**Key monitoring features:**

* Visual status indicators (pending, in progress, completed, failed)
* Execution time tracking for performance optimization
* Activity-level error messages for troubleshooting
* Pause, stop, or restart workflows as needed

Access monitoring from **[!UICONTROL Administration > Production > Objects created automatically > Campaign workflows]** or directly from the workflow dashboard.

**Related topics:**

* [Monitor workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}
* [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Start a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html){target="_blank"}

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

* [Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}
* [Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

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

* [Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Targeting workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html){target="_blank"}
* [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Personalization guide](../send/personalize.md)
* [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}
* [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

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

* [Split activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"}
* [A/B testing guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

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

* [Import data guide](../start/import.md)
* [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"}
* [Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

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

* [Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}
* [Using aggregates](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}
* [Welcome programs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}

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

* [Targeting activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"}
* [Flow control activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"}
* [Action activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}
* [Event activities reference](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html){target="_blank"}

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

* [Workflow best practices guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}
* [Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}
* [Monitor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

## Campaign Settings {#settings}

Configure your Campaign instance with the right settings, integrations, and configurations to optimize your marketing operations.

+++ Can I change the language of Campaign interface?

Campaign language is selected when creating the instance. You cannot change it afterwards. For more on this, refer to [this section](../start/connect.md).

Adobe Campaign user interface is available in multiple languages: English, French, German, Japanese, and more. Please note that the client console and the server must be set with the same language. Each Campaign instance can only run in one language.

For English, when installing Campaign, you can select either US English or UK English: they differ on date and time formats.

+++

+++ Can I use Campaign v8 with other Adobe solutions?

You can combine the delivery functionalities and advanced campaign management functionalities of Adobe Campaign with a set of solutions created to help you personalize your users' experience.

[Learn how to work with other Adobe solutions](../connect/integration.md) and [how to set up IMS in Campaign](../start/connect.md).

+++

+++ How can I set up tracking capabilities on my Campaign instance?

As an experienced user, you can configure tracking capabilities on your Campaign instance.

[Learn more](../start/tracking.md).

+++

+++ How to configure email deliverability?

In addition to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}, review the deliverability technical recommendations to understand how to configure your instance in order to maximize Campaign delivering capabilities.

[Learn more](../send/about-deliverability.md).

+++

+++ How can I implement content approval?

Campaign lets you set up approval processes for the main steps of the marketing campaign, in collaborative mode. For each campaign you can approve the delivery target, contents and costs. Adobe Campaign operators in charge of approval can be notified by email and can accept or reject approval from the console or via a Web connection.

[Learn more](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html){target="_blank"} and discover steps to implement your delivery content approval in Campaign.

+++

+++ How can I access data stored in an external database?

Adobe Campaign provides the Federated Data Access (FDA) option in order to process information stored in one or more external databases: you can access external data without changing the structure of Adobe Campaign data.

[Learn more](../connect/fda.md).

+++

+++ Which external databases can I connect Campaign to?

External database compatible with Campaign through Federated Data Access (FDA) are listed in the [Compatibility matrix](compatibility-matrix.md).

+++

+++ Can Adobe Campaign integrate with CRM systems?

Adobe Campaign provides various CRM connectors for linking your Adobe Campaign platform to your third-party systems. These CRM connectors enable you to synchronize contacts, accounts, purchases, etc. They make for easy integration of your application with various third-party and business applications.

These connectors enable quick and easy data integration: Adobe Campaign provides a dedicated assistant for collecting and selecting from the tables available in the CRM. This guarantees two-directional synchronization to make sure data is up-to-date at all times throughout the systems.

[Learn more](../connect/crm.md) about how to synchronize your CRM tool with Adobe Campaign.

+++

+++ How do I clear the client console cache?

If you have issues such as new logos not being reflected correctly, or issues with exporting data, you might need to clear the client console cache.

Sign out and close the client console. Navigate to the following location based on your operating system:

* Windows: `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* Mac: `~/Library/Application Support/Neolane/NL_5/`

Delete the XML configuration files (keeping `nlclient_cnx.xml`), then log back in to the client console.

+++

+++ Can I configure user interface settings?

Yes, as an administrator, you can customize Campaign UI settings for your users. [Learn more](../config/ui-settings.md).

+++

+++ Can I create custom fields and tables?

Yes, Campaign v8 allows you to extend the data model with custom fields and tables. Learn how to [extend schemas](../dev/extend-schema.md).

+++

## Reporting {#reporting}

Get insights into Campaign's reporting capabilities, including built-in reports, custom reports, and data analysis tools like cubes.

+++ How can I create new reports?

In addition to built-in reports, Adobe Campaign lets you generate reports in various contexts and to meet different needs.

Adobe Campaign is not a specialized reporting tool: reports created in Adobe Campaign mainly enable you to view aggregated data.

[Learn more](../reporting/gs-reporting.md) about Campaign reporting capabilities.

+++

+++ How can I design and share statistic reports on populations?

Adobe Campaign [descriptive analysis reports](../reporting/built-in-reports.md) allow you to design and share statistic reports on your populations.

[Learn more](../reporting/built-in-reports.md).

+++

+++ How can I design advanced reports on my data?

With Campaign v8, you can [create advanced reports](../reporting/custom-reports.md). As an expert user, you will be able to build, update and distribute custom reports on your data.

You can also use the Campaign Web user interface to create reports and dashboards. [Learn more](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}.

+++

+++ What is a cube and how to create such a report?

You can extend the database exploration and analysis capacities while making it easier for final users to configure reports and tables: all they need to do is select an existing (fully configured) cube when creating their report or table to process calculations, measures and statistics.

Once they have been created and configured, cubes are used in report query boxes and Web applications. They can be used and manipulated within pivot tables.

Learn how to [explore your data](../reporting/gs-cubes.md) with cubes.

+++

+++ Can I create a report from answers to an online survey?

Campaign v8 does not have a built-in survey feature. You can use Adobe Experience Manager or other web solutions for creating surveys. 

However, you can use reporting capabilities to analyze any collected data and create custom reports.

+++

+++ How can I share access to my report in Campaign interface?

You can define in which context your report will be displayed in the Adobe Campaign UI. For more on report access, refer to [this section](../reporting/custom-reports.md).

+++

+++ Can I export reports in different formats?

Yes, you can export Campaign reports in different formats such as Excel, PDF, or CSV. [Learn more](../reporting/custom-reports.md).

+++

## Developers {#developers}

Access technical information for developers, including data model details, schemas, APIs, and customization capabilities.

+++ What is the Campaign data model?

The conceptual data model of the Adobe Campaign database consists in a set of built-in tables and their interaction. The physical and logical structure of the data carried in the application is described in XML. It obeys a grammar specific to Adobe Campaign, called a schema. 

[Learn more about Campaign data model](../dev/datamodel.md).

[This page lists best practices](../dev/datamodel-best-practices.md).

+++

+++ How to work with Campaign schemas?

In Adobe Campaign, data schemas are used to:

* Define how data objects within the application are tied to underlying database tables.
* Define links between the different data objects within the Campaign application.
* Define and describe the individual fields included in each object.

[Get started with tables and schemas](../dev/schemas.md) to understand how to work with data schema, extend and customize Campaign to address your needs.

+++

+++ How to use a custom recipient table?

You can create and implement a non-built-in recipient table in Campaign to send your messages.

[Learn more](../dev/custom-recipient.md)

+++

+++ What are the best practices to define queries in Campaign?

Adobe Campaign query editor is a powerful tool to explore data and build segments.

The Adobe Campaign query tool can be found on multiple levels of the software: to create a target population, segment customers, extract and filter tracking logs, build filters, etc.

You can query Campaign database using the generic query editor. It is accessed via the **Tools > Generic query editor...** menu. It lets you extract information stored in a database and organize, group, sort, etc. For instance, the user can recover recipients who clicked more than 'n' times on the link of a newsletter over a given period. This tool lets you collect, sort and display results based on your needs.

[Learn more](../start/query-editor.md). You can also consult the [Campaign Automation guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

+++

+++ How can I import a data package?

Adobe Campaign allows you to export or import the platform configuration and data through a package system. Data packages let entities of the Adobe Campaign database be displayed via files in XML format. Each entity contained in a package is represented with all of its data.

The principle of data packages is to export a data configuration and integrate it into another Adobe Campaign system.

[Learn more](../dev/packages.md) about how to work with data packages to import and export Campaign configurations.

+++

+++ Where can I find the list of Campaign v8 APIs?

All Campaign APIs including their full description is available in this [dedicated documentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html){target="_blank"}.

+++

+++ What is the Campaign REST API?

Campaign v8 exposes a set of REST APIs that let you create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use.

[Learn more](../dev/api/get-started-apis.md).

+++

+++ How do I monitor workflows from API?

Learn how to monitor workflows using Campaign APIs in [this dedicated page](../dev/api/controlling-a-workflow.md).

+++

+++ How can I update the database structure?

If you modify Campaign data schemas, you need to update the database structure. Learn how in [this section](../dev/update-database-structure.md).

+++

+++ What are the limitations of Campaign v8?

Campaign v8 comes with some limitations compared to Campaign Classic v7, detailed in [this page](../start/v7-to-v8.md#limitations).

+++

## Privacy {#privacy}

Understand how Adobe Campaign helps you comply with privacy regulations like GDPR and CCPA, and manage data subject requests.

+++ What are the key terms about Privacy?

The items listed below link to the key terms and concepts related to Privacy and Consent in Adobe Campaign:

* [Regulations on Privacy management](../start/privacy.md#privacy-regulations)
* [Personal Data and Personas](../start/privacy.md#personal-data)
* [Right to Access and Right to be Forgotten](../start/privacy.md#right-access-forgotten)
* [Consent, Retention and Roles](../start/privacy.md#consent-retention-roles)

+++

+++ What is Adobe Campaign's suggestion to comply with the most recent Privacy regulations?

Adobe does not provide legal advice. You should work with your own legal counsel to ensure they are taking all steps necessary towards GDPR, CCPA, PDPA, LGPD or any other applicable regulation readiness.

**Prepare for data Access and Delete requests**

* Identify a process to receive/respond to Data Subject requests, including appointing a Privacy point of contact.

* Review the various customer data stored in Adobe Campaign and determine unique identifiers (there will likely be more than one).

* Determine a validation/authentication policy and process for Data Subject identity confirmation.

* Make sure that the Data Subject response is easy to understand.

**Consider Consent**

* List and update as necessary all touch points for data capture for GDPR (i.e. consider language, mechanism for consent, and consent logs).

* Make sure all marketing emails include the unsubscribe links.

* Assess global strategy for email marketing to determine geo-specific implementations.

**Understand your data**

* Review all data import and capture sources where data is flowing into Adobe Campaign, and document which fields are being used for your marketing efforts.

* Remove any unused data attributes from your Adobe Campaign database.

* Use data available in Adobe Campaign for the intent it was captured and give your recipients better personalized experiences.

* Review and update data access permissions to help ensure users of Adobe Campaign can fully leverage only the data needed to run their campaigns, but not access any data beyond this.

* Ensure each user of Adobe Campaign has the appropriate access rights to perform their required tasks, but does not have any other rights to perform additional tasks.

+++

+++ How could Data Controllers obtain consent with minimal impact on user engagement?

In those instances where consent will be needed for certain marketing activities, consumer consent will need to be active (i.e. no silence as assent or pre-checked boxes), unbundled, and it may not be conditional upon offering the services.

There may even be instances where certain consents need to be refreshed to be able to continue using data going forward.

Marketers should embrace these enhanced consent requirements as a true indicator of brand engagement and loyalty, as well as customer satisfaction and trust.

+++

+++ How can Data Controllers manage consent in Adobe Campaign?

Adobe Campaign already provides capabilities to manage consent at more levels than most marketers leverage via customized data fields or through one or more services.

Marketers should check with their legal counsel for guidance on how to proceed, and then take advantage of capabilities already built-in to Adobe Campaign.

For example, extending the data model in Adobe Campaign to track not only if people have opted-in, but also the timestamp of the opt-in, and some type of indicator that captures the precise scope of consent.

+++

+++ What data can Data Controllers delete in Adobe Campaign in response to a customer request by a Data Subject?

All data associated to the Data Subject will be deleted including out-of-the-box and custom tables.

Technically, all data linked to the Data Subject with `integrity="own"` will be deleted.

As the Data Controller, you have the option of customizing this by changing the integrity of links defined in the data schemas (for example, in case you have a business justification to not delete certain data).

+++

+++ How are reports affected when delivery and tracking logs are deleted?

Reports in Adobe Campaign are based on indicators computed on aggregated data from delivery and tracking logs. As a result, removing the individual logs should not impact the metrics displayed on the reports.

+++

+++ Do I need to be mindful of possibly re-importing data at a later date?

In Adobe Campaign, records are often uploaded from an external data source.

As the Data Controller you will need to ensure that when you receive a deletion request, you delete all necessary data about the Data Subject from all of your systems.

+++

+++ Can a Data Subject, whose data has been erased from Adobe Campaign, opt in again later?

It is possible for a Data Subject to opt-in again or to be added as a new recipient after their data has been erased from Adobe Campaign.

You can use the audit trail which details when the previous deletion was performed and when the new recipient has been created.

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

* **[Campaign v8 Documentation Home](campaign-home.md)** - Complete product documentation
* **[Campaign Tutorials](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html){target="_blank"}** - Step-by-step video guides and hands-on tutorials
* **[What's New](whats-new.md)** - Latest features and capabilities
* **[Release Notes](release-notes.md)** - Current and previous release information
* **[Best Practices](delivery-best-practices.md)** - Recommended approaches for common tasks

### Technical Resources

Find detailed technical documentation and developer resources.

* **[Campaign APIs](https://experienceleague.adobe.com/developer/campaign-api/api/index.html){target="_blank"}** - Complete API reference documentation
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** - Contribute to documentation
* **[Technical Notes](https://experienceleague.adobe.com/en/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - In-depth technical articles
* **[Compatibility Matrix](compatibility-matrix.md)** - Supported systems and versions

### Support & Services

Get help from Adobe's support team and manage your instance.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Log support cases and manage users
* **[Adobe Customer Care](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contact the support team
* **[Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html){target="_blank"}** - Manage your Campaign instance settings
* **[System Status](https://status.adobe.com/){target="_blank"}** - Check Adobe services status

### Training & Certification

Advance your skills with official Adobe training and certification programs.

* **[Adobe Digital Learning Services](https://learning.adobe.com/){target="_blank"}** - Official instructor-led and self-paced courses
* **[Adobe Campaign Certification](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Validate your expertise with professional certification
* **[Experience League Learning Paths](https://experienceleague.adobe.com/?lang=en#dashboard/learning){target="_blank"}** - Guided learning journeys

### Other Helpful Resources

* **[Campaign Classic v7 Documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html){target="_blank"}** - Reference for Classic v7 users
* **[Campaign Web UI Documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - New web interface guide
* **[Deliverability Best Practices](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}** - Optimize email delivery
* **[Product Updates](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - Latest Adobe Experience Cloud updates

**Last updated:** November 2025 | **Applies to:** Campaign v8.6 and later

*Found an error or want to suggest an improvement? [Edit this page on GitHub](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

