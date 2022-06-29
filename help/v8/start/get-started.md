---
title: Get started with Campaign v8
description: New to Campaign? Discover how to get started
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
---
# Get Started with Adobe Campaign{#gs-ac-v8}

Adobe Campaign provides a platform for designing cross-channel customer experiences and an environment for visual campaign orchestration, real-time interaction management and cross channel execution.

Use Campaign to:

* **Drive** personalization and engagement through a single accessible view of the customer
* **Integrate** email, mobile, online and offline channels into the customer journey
* **Automate** the delivery of meaningful and timely messages and offers

![](assets/ac-capabilities.png) 

## Integrated customer profile {#integrated-customer-profile}

Profiles are centralized in a powerful cloud database. There are many possible mechanisms for acquiring profiles and building up this database: on-line collection via web forms, manual, or automatic import of text files, replication with company databases or other information systems. With Adobe Campaign, you can incorporate marketing history, purchase information, preferences, CRM data, and any relevant PII data in a consolidated view to analyze and take action.

In Adobe Campaign, recipients are the default profiles targeted for sending deliveries (emails, SMS, etc.). Thanks to the recipient data that are stored in the database, you will be able to filter the target that will receive any given delivery and to add personalization data in your delivery contents. Other types of profiles exist in the database. They are designed for different uses. For example, seed profiles are made to test your deliveries before they are sent to the final target.

![](../assets/do-not-localize/glass.png) Profile management basics are explained in [this section](audiences.md).

![](../assets/do-not-localize/glass.png) Learn how to add profiles to Campaign in [this section](import.md).

## Targeted segmentation {#targeted-segmentation}

Adobe Campaign has powerful, user-friendly segmentation and targeting features that let you create highly targeted, differentiated offers. The descriptive analysis functionality lets you analyze information upstream and downstream of your marketing campaigns, and the filter management and graphical query editor functionality lets you filter your subscriber population and sample or create target groups based on an unlimited number of criteria. 

The advanced Data Management functionality extends the data processing capabilities. It simplifies and optimizes the targeting process by including data not modeled in the datamart. 

![](../assets/do-not-localize/glass.png) Learn more about segmentation, audience creation and personalization in [this section](audiences.md).

## Cross-channel campaign orchestration {#cross-channel-campaign-orchestration}

Adobe Campaign lets you design and orchestrate targeted and personalized campaigns on multiple channels: email, direct mail, SMS, push notification. A single interface provides you with all the functions required to schedule, orchestrate, configure, personalize, automate, execute, and measure all your campaigns and communications. 

![](../assets/do-not-localize/glass.png) Learn how to design, schedule and execute a campaign in [this section](campaigns.md).

## Workflows

Adobe Campaign offers a comprehensive graphical environment that allows you to design complex processes including segmentation, campaign execution, file processing, etc. For example, you can use a workflow to download a file from a server, decompress it, and then import its records into the Adobe Campaign database.

A workflow can also involve users by assigning them tasks or having them approve performed tasks. This means you can assign a task to one or several users to work on content or specify targets, and approve proofs before sending the message.

Workflows can be used in different contexts, as for example:

* Targeting to manage audiences or send messages.
* Data management (ETL) to manipulate data.
* Importing data into Campaign database.
* Technical processes such as database cleanup, recovering tracking information, etc.

![](../assets/do-not-localize/glass.png) Learn how to design and execute workflows in [this section](../config/workflows.md).

## Reporting and analysis {#analysis-and-reporting}

Adobe Campaign lets you monitor and interpret the behavior of your customers by gradually enriching their data and profiles. The reporting and analysis tools let you capitalize on each new campaign, target your marketing initiatives better, and optimize their impact and return on investment. 

In addition to powerful, out-of-the box reporting templates, Adobe Campaign lets you create custom reports on a delivery, campaign, user, or segment level. Do descriptive analysis, summarize ROI, or export data to Adobe Analytics and other solutions for further data visualization and analysis.

The campaign reporting feature facilitates the creation of dynamic reports. You can use drag-and-drop variables to customize your reports and to analyze the success of your campaigns. Depending on the complexity of your queries and calculations, the data can be aggregated into a list view or accessed in a format that makes it easy to generate marketing analytics reports.


![](../assets/do-not-localize/glass.png) Learn more about report and tracking capabilities in [this section](reporting.md).

## Adobe Experience Cloud integrations {#adobe-experience-cloud-integrations}

You can combine the delivery functionalities and advanced campaign management functionalities of Adobe Campaign with a set of solutions created to help you personalize your users' experience: Adobe Experience Manager, Adobe Analytics, Adobe Target or Adobe Experience Cloud triggers for example.  

![](../assets/do-not-localize/glass.png) Learn how to integrate with Adobe services and solutions in [this section](../connect/integration.md).

## More about Campaign capabilities {#core-capabilities-and-add-ons}

Adobe Campaign offers a set of capabilities to help you implement and optimize the conversational marketing functionalities depending on your needs and your architecture. Some of them are core capabilities and some depend on the installation of a package on your configuration. A detailed product description is available here: [Adobe Campaign v8 Product Description](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html).

![](../assets/do-not-localize/glass.png) Already familiar with Campaign Classic? Learn key differences between Campaign Classic and Campaign v8 in [this page](v7-to-v8.html).

**See also**

* [Campaign workspace](campaign-ui.md)
* [Campaign v8 Compatibility matrix](compatibility-matrix.md)
* [Connect to Campaign](connect.md)
* [Frequently Asked Questions](campaign-faq.md)