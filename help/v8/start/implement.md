---
title: Implementation guidelines
description: Learn how to implement Campaign v8
feature: Overview
role: User, Admin, Developer
level: Beginner, Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
---
# Campaign implementation guidelines

In this section, you will learn how to adjust Adobe Campaign to the requirements of your company. Use the following guidelines to structure and organize your implementation. 

1. **Define settings**: grant access, share the Client Console, configure channels (email, push, sms)
1. **Prepare your environment**: import profiles, create audiences, design workflow and campaign templates, create typology rules
1. **Customize your instance**: create new data fields, add tables/schemas
1. **Extend your deployment**: connect to Adobe solutions, other products and systems - connectors, multi-solution settings

>[!CAUTION]
>
>With **Campaign Managed Cloud Services**, your environment and initial configuration have been set by Adobe, according to the terms of your license agreement. You are not allowed to modify installed built-in packages, built-in schemas or reports. 
>
>If you need to use a Campaign add-on or a specific capability which has not been provisioned for you, you must contact **Adobe Customer Care**.

## Before starting

This section contains critical information about privacy and security that needs to be reviewed and taken into account before even starting the actual implementation.

### Privacy

Adobe Campaign comes with processes and settings that allow you to use Campaign in compliance with applicable data privacy laws and your recipient's preferences. You can manage: 

* **Data acquisition**: Adobe Campaign enables you to collect data, including personal and sensitive information. It is therefore essential that you receive and manage consent from your recipients. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition){target="_blank"}

* **User consent and data retention**: Learn how to get user consent, set up double opt-in subscription mechanisms, facilitate opt-out and configure data retention in [Campaign Classic privacy documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent){target="_blank"}

* **Privacy and data protection regulations**: refer to [this section](privacy.md) for information about privacy requirements, and how these regulations impact your organization and Adobe Campaign.

### Security

Learn security guidelines and principles with Adobe Campaign in [Campaign Security checklist](../config/security.md).

## Define Campaign settings

### Add users and grant permissions

You can manually add users to Campaign and associate them with groups, aligned with your role hierarchy. Users will then be able to log in and access the data and permissions which are appropriate for them.

![](../assets/do-not-localize/book.png) Learn how to add users to Adobe Campaign in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started){target="_blank"}.

### Install Campaign Client Console

The main user interface of the application is a rich client, in other words, a native application (Windows) that communicates with the Adobe Campaign application server solely with standard internet protocols (SOAP, HTTP, etc.). Adobe Campaign Client Console provides great user-friendliness for productivity, uses very little bandwidth (through the use of a local cache) and is designed for easy deployment. This Console can be deployed from an internet browser, can be updated automatically and does not require any specific network configuration because it only generates HTTP(S) traffic. 

![](../assets/do-not-localize/glass.png) [Learn more about Campaign Client Console](connect.md).

## Prepare your environment

Before starting sending messages and creating marketing campaigns, you need to:

1. Import profiles and create audiences

    Campaign helps you add contacts to the Cloud database. You can load a file, schedule and automate multiple contact updates, collect data on the Web, or enter profile information directly into the recipient table. 

    ![](../assets/do-not-localize/glass.png) [Learn how to import profiles](import.md).
    
    Audiences are grouped into lists and can be created through workflows. They can then be targeted in cross-channel deliveries.

    ![](../assets/do-not-localize/glass.png) [Learn how to define audiences](audiences.md).

1. Create templates

    Campaigns, deliveries, jobs or workflows are all based on a template, which stores key settings and capabilities. A built-in template is supplied for each component, for which no specific configuration has been defined. You need to configure and adapt templates to your needs and make them available to end-users.


   ![](../assets/do-not-localize/glass.png) Learn how to work with campaign templates in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html)

   ![](../assets/do-not-localize/glass.png) Learn how to configure a workflow template in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html)
   
    ![](../assets/do-not-localize/book.png) Learn more about email templates in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}


1. Configure typology rules

    Leverage Campaign typologies rules to filter, control and monitor delivery sending. For example, fatigue rules control frequency and quantity of messaging to avoid over-solicitation of recipients. Once implemented, typology rules are referenced in deliveries. 

   Learn more about typologies and fatigue management in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html).

1. Get familiar with Campaign built-in data model

    Adobe Campaign comes with a pre-defined data model. To implement and customize your environment, you need to be familiar with the built-in tables of the Adobe Campaign data model and how they relate to each other.

    ![](../assets/do-not-localize/glass.png) [Learn more about Campaign datamodel](../dev/datamodel.md).

## Customize your instance

You can customize many different Campaign areas and capabilities. Most of our customers customize three things:

1. **Tables and schemas**

    Adobe Campaign comes with common schemas to identify data such as: recipients, delivery logs, subscriptions, and more. 
    
    ![](../assets/do-not-localize/glass.png) Refer to this section to learn more about [Campaign built-in datamodel](../dev/datamodel.md).
    
    ![](../assets/do-not-localize/glass.png) You can extend existing schemas or create new schemas from scratch. Learn more in [this page](../dev/customize.md).
    
1. **Dashboards and lists**

    You can easily configure lists, add and remove fields and customize columns.
    
    ![](../assets/do-not-localize/glass.png) Learn how to manage filters and lists in Campaign in [this page](../dev/customize.md#gs-lists-and-filters).

    You can also create new dashboards to display Campaign data depending on your needs. 
    
    ![](../assets/do-not-localize/glass.png) Learn more in [this page](../dev/customize.md#gs-custom-dashboards).

1. **Reports**

    Campaign provides a set of built-in reports on delivery monitoring, URLs and click streams, tracking, deliverability indicators, and more.

    In addition to built-in reports, Adobe Campaign lets you generate reports in various contexts and to meet different needs. Principles of use and implementation modes are detailed in this document.

    ![](../assets/do-not-localize/glass.png) Learn more about reporting capabilities in Campaign in [this page](../reporting/gs-reporting.md).


## Set up campaign automation

To orchestrate complex marketing campaigns to different audiences across multiple channels, leverage Campaign automation capabilities. 

* Workflows: manage processes and data

* Subscriptions and landing pages

* Typology rules: fatigue and control management 

## Extend your deployment

### Multi-solutions implementation

If you are using other Adobe solutions, you can connect them to your Campaign environment and combine capabilities.

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Experience Cloud Triggers
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Analytics Data connectors


You can also use Single Sign-On (SSO) to connect to Campaign. Learn more in [this page](connect.md).

![](../assets/do-not-localize/glass.png) Discover the full list of Adobe solution which can be integrated with Adobe Campaign [in this page](../connect/integration.md).

### Connectors

Connect Campaign with third-party systems to combine a large range of capabilities and automate processes. 

![](../assets/do-not-localize/glass.png) Learn more about available connectors in [this section](../connect/integration.md).

**Connect your CRM to Campaign**

You can connect your Adobe Campaign platform to your CRM third-party systems and synchronize data: contacts, accounts, purchases, etc.  

![](../assets/do-not-localize/glass.png) Learn how to connect your CRM system to Campaign in [this section](../connect/integration.md#gs-crm-connectors)

**Connect to an external database**

You can connect Campaign Cloud database to external systems through the Federated Data Access (FDA) module. 

![](../assets/do-not-localize/glass.png) Learn how to configure Campaign FDA module to define access parameters in [this section](../connect/integration.md#gs-fda)
