---
title: Campaign v8 Frequently Asked Questions
description: Get answers to common Adobe Campaign v8 questions about setup, configuration, messaging, workflows, and more
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, answers, help, support, troubleshooting
version: Campaign v8
---
# Frequently Asked Questions {#faq}

Get quick answers to the most common questions about Adobe Campaign v8. Whether you're just getting started or looking for advanced configuration help, you'll find answers organized by topic below.

**New to Campaign?** Start with [Getting Started](#getting-started) to learn the essentials.  
**Need help with versions?** Check [Upgrades](#upgrades) for version information and upgrade processes.  
**Migrating from v7 or Standard?** See [Campaign v8 vs Previous Versions](#v7-differences) for differences and transition guidance.  
**Need technical help?** Check [Developers](#developers) and [Campaign Settings](#settings).  
**Can't find your answer?** Visit our [Community Forums](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} or [contact support](#get-help).

**Tip:** Use Ctrl+F (Cmd+F on Mac) to search for specific keywords on this page. Click any question to expand the answer.


## Getting Started {#getting-started}

Learn the essentials to start working with Adobe Campaign v8, from installation and connection to creating your first campaigns.

+++ What is Adobe Campaign v8?

Adobe Campaign v8 is a powerful cross-channel marketing automation platform that helps you create, coordinate, and deliver personalized campaigns across email, mobile, social, and offline channels. It combines a robust marketing database, campaign orchestration engine, and real-time interaction capabilities to engage customers throughout their journey.

**Key capabilities:** Multi-channel campaign management, audience segmentation and targeting, workflow automation, personalization at scale, real-time and batch messaging, reporting and analytics, integration with Adobe Experience Cloud.

**What makes v8 unique:** Cloud-native architecture (Managed Cloud Services only), enterprise-scale performance powered by Snowflake database, automatic upgrades, enhanced security, and bi-directional integration with Adobe Experience Platform.

**Ideal for:** Enterprise marketing teams managing complex, high-volume campaigns across multiple channels and customer touchpoints.

**Related topics:**

[Campaign v8 product description](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [What's new in v8](whats-new.md) | [Get started guide](get-started.md)

+++

+++ How can I download Campaign?

You can get the installation program and the client console from Adobe Download Center.
    
As an Admin user, access Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} to download Adobe Campaign.
    
Learn more about the Distribution Center [on this page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

+++

+++ How can I connect to Campaign v8?

You need to download and install Campaign client console to connect to Adobe Campaign. [Learn more](connect.md).

Starting Campaign v8.6 release, you have access to the **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. 

Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui). Learn more in the [Adobe Campaign Web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Related topics:**

[Install the client console](connect.md) | [Campaign user interface](campaign-ui.md) | [User permissions](gs-permissions.md)

+++

+++ Can I connect to Campaign v8 with an Adobe ID?

Yes! Thanks to the integration with the IMS (Adobe Identity Management System), users connect to the Adobe Campaign console using their Adobe ID. This integration provides the following advantages:

* The same ID can be used for all Experience Cloud solutions.
* The connection is memorized when using Adobe Campaign with different integrations.
* Securer password management policy.
* Use of Federated ID accounts (external ID provider).

[Learn more](connect.md) about accessing Campaign v8 with an Adobe ID.

+++

+++ What are Campaign user interface concepts I should know?

Refer to [this section](campaign-ui.md) to learn more about Adobe Campaign user interface basics.

Starting Campaign v8.6 release, you also have access to the new **Campaign Web user interface**, available through the central Adobe Experience Cloud environment.

[Learn more in the Adobe Campaign Web user interface documentation](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ How can I set up user permissions?

As a Campaign administrator, you can set up permissions for users of your organization.

These are a set of rights and restrictions that authorize or deny to:

* Access to certain functionalities
* Access to certain data
* Create, modify and/or delete data

**Related topics:**

[Get started with permissions](gs-permissions.md) | [Manage user permissions](manage-permissions.md) | [Add permissions on folders](folder-permissions.md)

+++

+++ How can I select the audience of my messages?

Campaign offers multiple targeting methods to select the right audience for your messages:

**Targeting methods:**

* **Query editor** - Build audiences using visual filters on recipient attributes, behaviors, or demographics
* **Lists** - Use predefined static or dynamic recipient lists
* **File import** - Upload external recipient files for one-time campaigns
* **Workflows** - Create complex targeting logic with query, split, and enrichment activities
* **Predefined filters** - Apply ready-to-use filters (active customers, subscribers, VIPs)
* **Segments from Adobe Experience Platform** - Leverage unified profiles and real-time segments

You can combine multiple criteria (location, purchase history, engagement) and use exclusions, intersections, or unions to refine your audience.

**Related topics:**

[Define audiences in Campaign v8](../audiences/gs-audiences.md) | [Query editor](query-editor.md) | [Target mappings](../audiences/target-mappings.md)

+++

+++ How to create and send a first email?

Creating your first email in Campaign v8 is straightforward. You start from a template, select your target audience, design your content with personalization, test it with proofs, and then send. Campaign offers two interfaces for email creation: the full-featured **Client console** for advanced users and the modern **Campaign Web UI** for faster, more intuitive email building.

**5 key steps:**

1. **Create delivery** - Start from an email template or create from scratch
2. **Define audience** - Select recipients using queries, lists, or workflows
3. **Design content** - Use the email designer to create your message with personalization fields
4. **Send test proofs** - Validate rendering and content across devices and email clients
5. **Analyze and send** - Run delivery analysis to check for errors, then send your email

**Related topics:**

[Email design and validation](../send/email.md) | [Create first delivery](create-message.md) | [Delivery templates](../send/create-templates.md) | [Personalize content](../send/personalize.md)

+++

+++ How to translate an error message?

An error message is displayed in a foreign language? All error messages and their translation are listed in [this page](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html){target="_blank"}.

+++

+++ How can I log an issue?

To contact Adobe Customer Support, connect to [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} to create a case or start a chat session.

Requires individual accounts with correct permissions. If you can't log in, request access via Experience League. [Learn more](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Alternatively, join [Campaign Community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community){target="_blank"} to search for answers or ask experts.

+++

+++ Which systems and components Campaign v8 is compatible with?

You can get the list of all systems and components supported for the latest build of Campaign in [Adobe Campaign Compatibility matrix](compatibility-matrix.md).

+++

+++ Can I use Campaign v8 with other Adobe solutions?

Yes. Campaign v8 seamlessly integrates with Adobe Experience Cloud solutions for a unified marketing ecosystem.

**Key integrations:** Adobe Experience Platform (unified profiles, real-time data), Adobe Analytics (performance measurement), Adobe Target (personalization), Adobe Experience Manager (content management), Adobe Audience Manager (audience segments).

**Setup:** Requires Adobe IMS authentication, automatically configured for Campaign v8 Managed Cloud Services.

**Related topics:**

[Adobe Campaign integrations](../connect/integration.md) | [Connect with Adobe ID](connect.md)

+++

+++ What are the limitations of Campaign v8?

Campaign v8 brings significant performance improvements but has some architectural differences from Campaign Classic v7, especially in FFDA deployments.

**Key considerations:**

* **FFDA architecture** - Uses cloud database (Snowflake) with different data access patterns
* **Data updates** - Should be done in workflows, not via direct database access
* **Batch-optimized** - Optimized for batch operations rather than high-frequency individual updates
* **Not available in FFDA** - Surveys, Marketing Resource Management (MRM), some specific connectors

**Migration impact:** Custom code using direct database writes needs refactoring; API integrations may need adaptation for batch processing.

These limitations are evolving as Adobe enhances v8. Consult latest documentation for current status.

**Related topics:**

[Campaign v7 to v8 migration](../start/v7-to-v8.md#limitations) | [FFDA architecture](../architecture/enterprise-deployment.md)

+++

+++ As a Campaign Classic v7 user, can I migrate to Campaign v8?

Automated migration from an existing Campaign Classic v7 environment is not yet available. 

Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 

For more information about the migration process, reach out to your Adobe representative.

Learn more in the [Campaign v8 vs Previous versions](#v7-differences) section.

+++


## Upgrades {#upgrades}

Learn how to check your Campaign version, understand the upgrade process, and stay informed about new releases. Campaign v8 Managed Cloud Services handles upgrades automatically with minimal disruption.

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


## Campaign v8 vs Previous Versions {#v7-differences}

Understand the key differences between Campaign v8 and previous versions (Classic v7 and Standard), including architecture, deployment, migration paths, and feature changes. Whether you're coming from Campaign Classic v7 or Campaign Standard, learn what's new and how to transition smoothly.


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

Campaign v8 is Adobe's platform, ideal for organizations needing high-volume campaigns (20M operations/hour), modern web UI, cloud-native benefits, and long-term support.

**Key benefits:**

* **For Campaign Standard users** - Familiar Web UI, feature parity (Dynamic Reporting, REST APIs, Landing Pages), smooth data migration
* **For Campaign Classic v7 users** - Dual interface (console + Web UI), better performance, automatic upgrades, enhanced FFDA architecture

**Consider migrating if you:**

* Handle large data volumes or experience performance issues
* Want to reduce IT overhead and infrastructure management
* Need Adobe Experience Cloud/Platform integration
* Want future-proof technology with automatic updates

**Next steps:** Contact your Adobe representative to assess migration readiness and access migration tools.

**Related topics:**

[From Campaign Classic v7 to v8](v7-to-v8.md) | [Campaign Standard transition guide](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

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

Campaign v8 brings most v7/Standard capabilities with enhancements, but some terminology and features differ. You'll find a summary of key changes below.

**Key terminology changes (Campaign Standard → v8):**

* Custom resources → **Schemas** | Messages → **Deliveries** | Product users → **Operators**
* Security Groups → **Operator Groups** | Organizational units → **Folder Permissions**

**Campaign Web UI updates:**

* Recipients → **Profiles** | Seed addresses → **Test profiles** | Delivery analysis → **Delivery preparation**
* Lists → **Audiences** | Email Preview → **Simulate content**

**Not available in v8:**

* On-premise/hybrid deployments (Managed Cloud Services only)
* Direct database access (use APIs)
* Manual infrastructure management (Adobe managed)

**New features for Campaign Standard users:**

* Dynamic Reporting, Centralized Branding, REST APIs, Landing Pages improvements, Visual Fragments

**Related topics:**

[Capability matrix](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [v7 to v8 transition guide](v7-to-v8.md) | [Campaign Standard to v8 transition](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/acs-migration){target="_blank"}

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

+++ How do I create test profiles for my deliveries?

Test profiles (seed addresses) let you target recipients who don't match defined targeting criteria, allowing you to test your delivery before sending to your main audience. Add them via **[!UICONTROL Seed addresses]** in the delivery properties or use the **[!UICONTROL Seed addresses]** folder.

Learn more about [test profiles](../audiences/test-profiles.md).

+++

+++ How can I define the target population of a marketing campaign?

Campaign offers multiple targeting methods: build queries with visual criteria, target existing lists or segments, import recipients from external files (CSV, TXT), or apply pre-defined filters. You can combine criteria with AND/OR logic, exclude specific populations, use control groups, and split for A/B testing. Always preview your target population size before sending.

**Related topics:**

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


## Message Design {#design}

Learn how to design effective marketing messages in Campaign v8, including email templates, personalization techniques, and multilingual content. Design your messages in the client console or use the modern **Email Designer** in the Campaign Web UI for an enhanced visual editing experience.

+++ What are the best practices for designing emails in Campaign?

Key guidelines: ensure mobile-responsive design, use HTML 4.0/XHTML compatible code with inline CSS, optimize images (under 100KB) with alt text, use personalization merge fields, test across email clients before sending, and include a plain text version. Aim for total email size under 500KB for optimal deliverability.

**Related topics:**

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

+++ How can I personalize email subject lines?

Personalized subject lines significantly increase open rates. Campaign allows you to dynamically insert recipient data, apply conditional logic, and test variations to optimize engagement.

**Personalization techniques:**

* **Basic fields** - Insert firstname, lastname, location: `"<%@ firstName %>, exclusive offer for you"`
* **Conditional content** - Different subjects by segment: `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **Dynamic data** - Include purchase history, loyalty points, or account info
* **Emojis** - Add visual appeal (test across email clients first)

**Best practices:** Keep under 50 characters, test personalization tokens before sending, use A/B testing to optimize, avoid spam trigger words, include value proposition or urgency.

**Related topics:**

[Personalization fields](../send/personalization-fields.md) | [Conditional content](../send/conditions.md)

+++

+++ Can I send multilingual messages?

Yes. Campaign v8 offers multilingual capabilities, with the **Campaign Web UI** providing the easiest approach. The Web UI offers native multilingual delivery with language variants—add language variants to your delivery, and Campaign automatically sends the appropriate version based on recipient's preferred language. Available for email, push notifications, SMS, and transactional messages.

Key features: automatic content duplication, automatic language-based sending, default language fallback, and easy variant management.

The client console also supports multilingual content using conditional content and workflows, but requires more manual configuration.

**Related topics:**

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

**Related topics:**

[AI Assistant overview](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [AI Assistant use cases](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Brand alignment](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Testing and Sending Messages {#send}

Learn best practices for testing, validating, sending, and tracking your marketing messages to ensure successful campaign delivery.

+++ How to improve email deliverability?

Email deliverability, a critical component to every sender's marketing program success, is characterized by ever-changing criteria and rules. Effectively navigating in this digital world requires regular tuning of your email strategy, with consideration to key deliverability trends, to best reach your audiences.

Refer to this guide to learn [Deliverability Best Practices](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html){target="_blank"}

Learn how to implement deliverability in Campaign [in this guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html){target="_blank"}

**Related topics:**

[Get started with deliverability](../send/about-deliverability.md) | [Control message content](../send/control-message-content.md) | [Monitor deliverability](../send/monitoring-deliverability.md) | [SpamAssassin](../send/spamassassin.md)

+++

+++ How can I make sure my delivery is sent without errors?

**Before sending:** Run delivery analysis, send test proofs, review warnings, verify target count.

**During/after sending:** Monitor delivery dashboard (sent, delivered, bounces, errors), check delivery logs, track success/bounce rates, review quarantined addresses.

**Best practices:** Set up alerts, use waves for large volumes, test with small volumes first, clean recipient database regularly, monitor sender reputation.

**Related topics:**

[Track and monitor deliveries](../send/tracking.md) | [Delivery best practices](delivery-best-practices.md)

+++

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

Learn more in the [Seed addresses guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

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

+++ Can I run A/B tests on my deliveries?

Yes! Campaign allows you to run A/B tests (also called split tests) to optimize subject lines, content, sender names, send times, and more by comparing performance across different variants.

**What you can test:**

* **Subject lines** - Compare open rates across different subjects
* **Content variations** - Test different layouts, calls-to-action, or images
* **Sender information** - Test sender name or from address impact
* **Send time** - Identify optimal delivery windows
* **Personalization strategies** - Compare personalized vs. generic content

**How it works:**

1. Create your delivery and define test variants (up to 3)
2. Split your audience (typically 10-20% for test segments)
3. Campaign sends variants to test segments and tracks performance
4. Winning variant automatically sends to remaining audience (or you manually select winner)

**Available in:** Both Campaign Web UI and client console. Web UI offers simpler setup with visual comparison.

**Related topics:**

[Delivery analysis](../send/delivery-analysis.md) | [Send and track deliveries](../send/send.md)

+++

+++ What is a typology rule?

Typology rules are automated business logic applied during delivery analysis to validate and optimize message sending. They ensure compliance with marketing policies, protect deliverability, and prevent customer fatigue.

**Main rule types:**

* **Filtering rules** - Exclude recipients (blocklisted, unsubscribed, quarantined)
* **Pressure rules** - Control message frequency to avoid overwhelming recipients
* **Capacity rules** - Limit message volume for processing capacity or ISP limits
* **Control rules** - Check message validity (subject line, unsubscribe link, sender format)

Rules are grouped into typologies and applied during delivery analysis. Campaign can exclude recipients, block the delivery, or generate warnings based on the rules.

Learn more in the [Typology rules guide](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html){target="_blank"}

+++

+++ How can I send emails in waves?

Yes. Wave sending splits your delivery into multiple batches sent at scheduled intervals. This is essential for large-volume campaigns to balance server load, prevent ISP throttling, build sender reputation with new IPs, and manage opt-outs/bounces between waves.

**Configuration:**

In your delivery properties, enable wave sending and define the number of waves (or batch size), interval between waves, and wave distribution (linear or custom percentages). Campaign automatically divides your target population and sends each wave on schedule.

Use waves for large campaigns, monitor first wave performance before continuing, and allow sufficient time between waves to process bounces and opt-outs.

Learn how to [Configure wave sending](../send/configure-and-send.md#sending-using-multiple-waves)

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

[Link tracking guide](../send/tracking.md) | [Tracking best practices](../send/send.md)

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

[Delivery monitoring](../send/send.md) | [Tracking guide](../send/tracking.md)

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

+++ What is a workflow?

Adobe Campaign includes workflows to orchestrate the full range of processes and tasks across the different modules of the application server. This comprehensive graphical environment lets you design processes including segmentation, campaign execution, file processing, human participation, etc. The workflow engine executes and tracks these processes.

You can use a workflow, for example, to download a file from a server, decompress it, and then import records contained within into the Adobe Campaign database.

A workflow can also involve one or more operators to be notified or who can make choices and approve processes. In this way, it is possible to create a delivery action, assign a task to one or more operators to work on content, specify targets, and to approve proofs before starting the delivery.

[Learn more](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html){target="_blank"} about workflows. You can also read out [workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"}.

**Related topics:**

[Get started with workflows](../config/workflows.md) | [Build your first workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Monitor workflow execution](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

+++

+++ Can I monitor workflow execution?

Yes. Campaign provides multiple monitoring tools: workflow dashboard (real-time status and errors), workflow logs (detailed execution logs), heatmap (visualize activity and bottlenecks), audit trail (track modifications), and alerts (notifications for failures).

To monitor, open the workflow and click the **Logs** tab. Failed activities appear in red.

**Related topics:**

[Monitor workflow execution](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

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

+++ How can I automate recurring campaigns?

Use workflows with the **Scheduler** activity to automate campaigns that run on a regular schedule—daily, weekly, monthly, or custom intervals. Perfect for welcome emails, birthday messages, newsletter sends, abandoned cart reminders, and regular reporting.

**Setup pattern:**

1. **Scheduler** - Define frequency (e.g., "Every Monday at 9 AM")
2. **Query** - Select target audience with dynamic criteria
3. **Enrichment** (optional) - Add personalization data
4. **Delivery** - Configure your message (email, SMS, push)
5. **End** - Workflow completes and waits for next scheduled run

**Common automated campaigns:**

* **Welcome series** - Daily workflow to send onboarding emails to new subscribers
* **Birthday emails** - Daily check for recipients with birthdays, send personalized message
* **Re-engagement** - Weekly targeting of inactive users with win-back offers
* **Newsletters** - Scheduled weekly or monthly content distribution
* **Cart abandonment** - Hourly workflow to identify and message cart abandoners

**Tip:** Use **recurring delivery** type in workflows to track each execution separately and maintain historical reporting.

**Related topics:**

[Scheduler activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"} | [Recurring deliveries](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Campaign automation](https://experienceleague.adobe.com/docs/campaign/automation/home.html){target="_blank"}

+++

+++ How can I import data in Campaign?

**Methods:** Import wizard (one-time CSV/TXT), workflow-based import (**[!UICONTROL Data loading (file)]** activity for complex/recurring imports with transformations), REST APIs (programmatic/real-time sync).

**Best practices:** Test with small samples, use UTF-8 encoding, map fields correctly, apply deduplication, schedule large imports off-peak.

**Related topics:**

[Import best practices](../start/import.md) | [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Recurring import workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html){target="_blank"}

+++

+++ How can I ensure data quality during imports?

Data quality is critical for successful campaign execution. Poor data leads to delivery failures, wasted resources, and compliance risks. Campaign provides tools to validate, clean, and enrich data during the import process.

**Data validation steps:**

1. **Pre-import validation** - Verify file format, encoding (UTF-8), column mapping, required fields present
2. **Deduplication** - Use **[!UICONTROL Deduplication]** activity to identify and handle duplicates by email, ID, or custom keys
3. **Data enrichment** - Use **[!UICONTROL Enrichment]** activity to add missing data from existing Campaign tables
4. **Format standardization** - Normalize phone numbers, email addresses, dates, country codes using JavaScript or enrichment
5. **Validation rules** - Apply constraints (valid email format, mandatory fields, value ranges)

**Common issues and fixes:**

* **Character encoding errors** → Always use UTF-8 encoding
* **Date format mismatches** → Standardize to YYYY-MM-DD format
* **Invalid email addresses** → Use validation rules or JavaScript to filter
* **Duplicate records** → Always include deduplication activity before updates
* **Missing required fields** → Set default values or reject incomplete records

**Best practice:** Create a reusable "data quality" workflow template with standard validation and cleaning activities that you can apply to all imports.

**Related topics:**

[Data quality guide](../start/import.md) | [Deduplication activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html){target="_blank"} | [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ What are common workflow use cases in Campaign?

Workflows automate marketing processes including:

**Data management:** Import/load data, cleansing, enrichment, list management  
**Campaign automation:** Welcome series, birthday campaigns, re-engagement, cart abandonment  
**Advanced targeting:** A/B testing, dynamic segmentation, lead scoring, cross-channel orchestration  
**Monitoring:** Workflow/delivery monitoring, alerts, database maintenance  
**Integration:** CRM sync, API integrations, event-triggered workflows

**Related topics:**

[Workflow use cases library](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Build a workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html){target="_blank"} | [Workflow best practices](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"}

+++

+++ How can I update Campaign data with a workflow?

Use **[!UICONTROL Update data]** activity for bulk database operations: Insert (add new records), Update (modify existing), Insert or update (upsert), Delete (remove matching records).

**Common uses:** Update profile attributes, synchronize with external systems, maintain list memberships, clean/deduplicate data, apply bulk status changes.

Configure reconciliation keys for accurate matching and choose update options.

**Related topics:**

[Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"} | [Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ How can I leverage data management capabilities?

Data management activities enable sophisticated operations: Enrichment (add data from related tables), Split (segment populations), Deduplication (remove duplicates), Update data (bulk operations), Change dimension (switch targeting dimensions), Intersection/Union/Exclusion (combine/filter populations).

**Common uses:** Enrich with purchase/behavior data, segment audiences, remove duplicates, integrate external databases (FDA), create complex multi-table queries.

**Related topics:**

[Data management activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Enrichment activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html){target="_blank"}

+++

+++ Can I automate personalized messages sending?

Yes. Build automated workflows: Query (target audience) → Enrichment (add personalization data) → Split (optional segments) → Delivery (personalized messages) → Scheduler (recurring execution).

**Personalization:** Use profile data, behavioral data, conditional content, dynamic values. Common scenarios: birthday campaigns, cart abandonment, loyalty programs, win-back, event-triggered messages.

**Related topics:**

[Personalization guide](../send/personalize.md) | [Workflow use cases](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}

+++

+++ How can I split an audience in subsets with a workflow?

Use **[!UICONTROL Split]** activity to divide populations: Filtering conditions (age, location, VIP status), Percentage distribution (A/B testing), Limit records (first N, top X%), Data grouping (one subset per value).

**Common uses:** A/B testing, channel preference routing, progressive rollout, segment-specific messaging, load balancing. Each subset flows to separate transition for different processing.

**Related topics:**

[Split activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html){target="_blank"} | [A/B testing guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ How can I update recipient data from an external file?

Yes. Workflow: Data loading (file) → Enrichment (optional) → Reconciliation (match keys like email/ID) → Update data (update matched records, insert new if no match).

**Common uses:** Update profile attributes from CRM, refresh subscription statuses, synchronize loyalty points, update opt-in/opt-out preferences.

**Best practices:** Use unique identifiers, validate data first, test with samples, schedule regular updates.

**Related topics:**

[Import data guide](../start/import.md) | [Data loading activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html){target="_blank"} | [Update data activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html){target="_blank"}

+++

+++ How can I identify and target new recipients?

Query **[!UICONTROL Created date]** field to select recipients added within specific timeframe.

**Automated welcome workflow:** Scheduler (run daily) → Query (select new recipients) → Deduplication (optional) → Delivery (welcome message) → Update data (mark as "welcomed").

**Advanced:** Use aggregate functions to dynamically identify recent additions.

**Related topics:**

[Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"} | [Using aggregates](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html){target="_blank"}

+++

+++ How do I use workflow activities?

Four activity categories:

**Targeting:** Query, Split, Deduplication, Enrichment, Intersection, Union, Exclusion (define/refine audience)  
**Flow control:** Scheduler, Wait, Test, Fork, AND-join, OR-join, Jump (manage logic/timing)  
**Action:** Delivery, Update data, Data loading/extraction, JavaScript code (perform operations)  
**Event:** External signal, File collector, HTTP transfer (react to triggers)

Drag from palette, double-click to configure, connect with transitions.

**Related topics:**

[Targeting activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html){target="_blank"} | [Flow control](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html){target="_blank"} | [Action activities](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html){target="_blank"}

+++

+++ What are workflow best practices?

**Design:** Clear names, add labels/descriptions, group related activities, break complex processes into smaller workflows  
**Performance:** Limit query sizes, use temporary tables, schedule off-peak, avoid excessive loops  
**Error handling:** Add error paths, configure alerts, test with samples, review logs  
**Maintenance:** Archive obsolete workflows, version control, limit complexity (<20 activities), use templates  
**Security:** Apply permissions, clean temporary data, use variables not hardcoded values

**Related topics:**

[Workflow best practices guide](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html){target="_blank"} | [Monitor workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html){target="_blank"}

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

+++ What is the procedure for domain delegation?

A subdomain is a division of your domain that can be used to isolate your brands, or various types of traffic (transactional messages, marketing information, etc.).
    
>[!NOTE]
>
>As a Managed Cloud Services user, contact Adobe to delegate your subdomains to Adobe.

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

[Track and monitor deliveries](../send/tracking.md) | [Configure tracked links](../send/tracked-links.md) | [Test tracking](../send/testing-tracking.md)

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

Campaign v8 supports Federated Data Access (FDA) connections to major enterprise database systems (cloud databases, enterprise databases, data warehouses, big data platforms).

Supported database versions and connection requirements vary. Check the [Compatibility matrix](compatibility-matrix.md) for your Campaign v8 version to confirm support for specific databases and ensure proper licensing for FDA connectors.

See [Configure FDA connections](../connect/fda.md)

+++

+++ Can Adobe Campaign integrate with CRM systems?

Yes. Campaign provides native CRM connectors for bidirectional synchronization with major CRM systems. Syncs contact data, leads, accounts, delivery logs, tracking data, and engagement metrics. Supports scheduled, manual, and real-time (via API) synchronization modes.

Use Campaign's CRM connector assistant to map fields, select tables, and schedule sync. Check [Compatibility matrix](compatibility-matrix.md) for supported CRM versions.

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

Learn more in [Install and configure client console](connect.md)

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

Campaign offers multiple reporting options depending on your needs and technical expertise: built-in reports, descriptive analysis, custom reports in the client console, and cubes.

**Reporting options:**

* **Built-in reports** - Ready-to-use delivery, campaign, and tracking reports accessible from the **[!UICONTROL Reports]** tab
* **Descriptive analysis** - Quick statistical reports on any data with a wizard-driven interface
* **Custom reports** - Advanced reports built by technical users using the reporting editor
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

Use the client console to create advanced custom reports with complex analysis capabilities.

In the Client Console, you can:

* Build complex reports using SQL queries and custom calculations
* Create multi-page reports with charts, tables, and pivot tables
* Design conditional formatting and dynamic content
* Access the full Campaign data model and external databases (FDA)

Learn how to [Create custom reports (client console)](../reporting/custom-reports.md) 

+++

+++ What is a cube and how can I use it for reporting?

Cubes are multi-dimensional data structures that enable business users to explore and analyze Campaign data through pivot tables without technical skills. Think of them as pre-configured data models that simplify complex reporting. This reporting tool is available in both the client console and Campaign Web UI.

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

**Advanced analysis:**

* Access survey responses from the **[!UICONTROL Responses]** tab and export data
* Use **[!UICONTROL Survey responses]** activity in workflows to target recipients based on their answers
* Combine survey data with other Campaign data for segmentation and personalization
* Create custom reports and cubes for multi-dimensional survey analysis

**Related topics:**

[Get started with surveys](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Survey reports](https://experienceleague.adobe.com/en/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ How can I share access to my reports?

Control report visibility through folder permissions and named rights in Campaign.

**Access control methods:**

* **Folder permissions** - Place reports in folders with appropriate access for user groups
* **Named rights** - Assign rights to view, create, or modify reports
* **Display context** - Define where reports appear (Reports folder, campaign tabs, delivery screens)

**Setup:** Save report to specific folder → Configure folder access for operator groups → Define report properties and display context.

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

Campaign's data model is a schema-driven relational database structure consisting of built-in tables (recipients, deliveries, campaigns) that can be extended for your business needs.

**Key concepts:** Schemas (XML definitions), built-in tables, links (relationships), enumerations (value lists), extensions (custom fields/tables).

**Main schemas:** Recipient (`nms:recipient`), Delivery (`nms:delivery`), Workflow (`xtk:workflow`), Campaign (`nms:operation`), Tracking logs.

Understanding the data model is essential for workflows, queries, schema extensions, and integrations.

**Related topics:**

[Campaign data model](../dev/datamodel.md) | [Data model best practices](../dev/datamodel-best-practices.md)

+++

+++ How to work with Campaign schemas?

Schemas define Campaign's data structure in XML format, specifying table structure, field properties, relationships, indexes, and access control.

**Working with schemas:**

* **View:** Access via **[!UICONTROL Administration > Configuration > Data schemas]**
* **Extend:** Create extension schemas (e.g., `cus:recipient`) to add custom fields without modifying core schemas
* **Create:** Build new tables for business-specific data
* **Update:** Apply changes via **[!UICONTROL Tools > Advanced > Update database structure]**

**Common uses:** Add custom fields to recipient table, create custom tables, define relationships, implement business-specific models.

**Important:** Never modify built-in schemas directly. Always use extension schemas for upgrade compatibility.

**Related topics:**

[Get started with schemas](../dev/schemas.md) | [Extend a schema](../dev/extend-schema.md)

+++

+++ How to use a custom recipient table?

Use a custom recipient table when targeting B2B accounts, separate subscriber data, external systems, or multi-brand architectures instead of the standard recipient table.

**Implementation:** Create custom schema with mandatory fields (email, primary key, exclusions) → Configure target mappings → Update delivery templates → Adapt workflows/queries.

**Key considerations:** Must include required delivery fields, workflows/forms need adaptation, testing critical before production migration.

**Best practice:** Extend the standard recipient table first. Only use custom tables when truly necessary due to added complexity.

**Related topics:**

[Custom recipient table](../dev/custom-recipient.md) | [Target mappings](../audiences/target-mappings.md)

+++

+++ What are the best practices to define queries in Campaign?

Campaign's query editor builds database queries visually without SQL, used in workflow activities, delivery targeting, lists, reports, and filters.

**Best practices:**

* Start simple - build incrementally, test each step
* Use filtering dimensions - leverage table relationships
* Optimize performance - index queried fields, avoid complex calculations
* Reuse predefined filters for consistency
* Test with small samples first
* Document complex queries

**Common patterns:** Target delivery openers, find inactive contacts, segment by behavior, exclude previous recipients.

**Access:** **[!UICONTROL Tools > Generic query editor]** for ad-hoc exploration.

**Related topics:**

[Query editor](../start/query-editor.md) | [Query activity](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}

+++

+++ How can I import a data package?

Import packages via **[!UICONTROL Tools > Advanced > Import package]** in the client console. Packages contain Campaign configurations (schemas, workflows, typologies) and data for deploying between instances.

**Package types:** User package (custom configs), Platform package (Adobe-provided), Data package (actual data).

**Best practices:** Test in dev first, back up before importing, export from same/older version.

Learn more in [Work with data packages](../dev/packages.md)

+++

+++ Where can I find the list of Campaign v8 APIs?

Campaign v8 provides SOAP APIs (client console operations), REST APIs (modern integrations), and JavaScript APIs (workflow scripting).

**Common uses:** Integrate with CRM/ERP, automate campaigns, synchronize data, build monitoring solutions, create external interfaces.

**Access:** [Campaign v8 API documentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html){target="_blank"}

+++


+++ How do I monitor workflows from API?

Campaign APIs let you programmatically control workflows: start, pause/resume, stop, query status, retrieve logs, monitor activity progress.

**API endpoint:** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Commands:** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Use cases:** Build monitoring dashboards, implement automated alerting, orchestrate from external schedulers, create dependencies across instances, generate custom reports.

**Best practice:** Combine API monitoring with audit trail for comprehensive governance.

See [Control workflows via API](../dev/api/controlling-a-workflow.md)

+++

+++ How can I update the database structure?

After modifying schemas (adding fields, creating tables, changing data types), update the physical database structure via **[!UICONTROL Tools > Advanced > Update database structure]** to apply changes.

**When needed:** Adding fields, creating/extending tables, modifying field properties, adding/removing links, creating indexes.

**Important:** Backup first, test in dev, plan downtime for large changes, coordinate with Adobe support (Managed Cloud Services), note some changes may cause data loss.


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

Campaign automatically deletes all data linked to a data subject: recipient profile, delivery and tracking logs, custom data with ownership relationships, and subscription history.

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
* **[Versions and Upgrades FAQ](upgrades.md)** - Check your version and learn about upgrades

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

