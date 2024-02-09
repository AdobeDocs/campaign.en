---
title: Implementation guidelines
description: Learn how to implement Campaign v8
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
---
# Campaign implementation guidelines{#gs-implementation}

In this section, learn how to adjust Adobe Campaign to the requirements of your company. Use the following guidelines to structure and organize your implementation. 

1. **Define settings**: grant access, share the client console, configure channels (email, push, sms). [Learn more](#implementation-ac-settings)
1. **Prepare your environment**: import profiles, create audiences, design workflow and campaign templates, create typology rules. [Learn more](#implementation-prepare-your-env)
1. **Customize your instance**: create new data fields, add tables/schemas. [Learn more](#implementation-custom-your-instance)
1. **Automate your processes**: configure Adobe Campaign automation capabilities. [Learn more](#implementation-automation)
1. **Extend your deployment**: connect to Adobe solutions, other products and systems - connectors, multi-solution settings. [Learn more](#implementation-extend)

>[!CAUTION]
>
>With **Campaign Managed Cloud Services**, your environment and initial configuration is set by Adobe, according to the terms of your license agreement. You are not allowed to modify installed built-in packages, built-in schemas, or reports. 
>
>If you need to use a Campaign add-on or a specific capability which has not been provisioned for you, you must contact your **Adobe Transition Manager**.

## Before starting{#before-starting}

This section contains critical information about privacy and security that needs to be reviewed and taken into account before even starting the actual implementation.

### Privacy{#implementation-privacy}

Adobe Campaign comes with processes and settings that allow you to use Campaign in compliance with applicable data privacy laws and your recipient's preferences. You can manage: 

* **Data acquisition**: Adobe Campaign enables you to collect data, including personal and sensitive information. It is therefore essential that you receive and manage consent from your recipients. 
    
    Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#data-acquisition){target="_blank"}

* **User consent and data retention**: you must get user consent, set up double opt-in subscription mechanisms, facilitate opt-out and configure data retention.
    
    Learn more in [Campaign Classic v7 privacy documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#consent){target="_blank"}

* **Privacy and data protection regulations**: refer to [this section](privacy.md) for information about privacy requirements, and how these regulations impact your organization and Adobe Campaign.

### Security

Learn security guidelines and principles with Adobe Campaign in [Campaign Security checklist](../config/security.md).

## Define Campaign settings{#implementation-ac-settings}

### Add users and grant permissions{#implementation-add-users}

You can manually add users to Campaign and associate them with groups, aligned with your role hierarchy. Users will then be able to log in and access the data and permissions which are appropriate for them.

![](../assets/do-not-localize/glass.png) Learn how to add users to Adobe Campaign in [this section](../start/gs-permissions.md).

### Install Campaign client console{#implementation-install-console}

The main user interface of the application is a rich client, in other words, a native application (Windows) that communicates with the Adobe Campaign application server solely with standard internet protocols (SOAP, HTTP, etc.). Adobe Campaign client console provides great user-friendliness for productivity, uses very little bandwidth (through the use of a local cache) and is designed for easy deployment. This Console can be deployed from an internet browser, can be updated automatically and does not require any specific network configuration because it only generates HTTP(S) traffic. 

![](../assets/do-not-localize/glass.png) [Learn more about Campaign client console](connect.md).

## Prepare your environment{#implementation-prepare-your-env}

Before starting sending messages and creating marketing campaigns, you need to:

1. **Import profiles and create audiences**

    Campaign helps you add contacts to the Cloud database. You can load a file, schedule and automate multiple contact updates, collect data on the Web, or enter profile information directly into the recipient table. 

    ![](../assets/do-not-localize/glass.png) [Learn how to import profiles](import.md).
    
    Audiences are grouped into lists and can be created through workflows. They can then be targeted in cross-channel deliveries.

    ![](../assets/do-not-localize/glass.png) [Learn how to define audiences](audiences.md).

1. **Use templates**

    Campaigns, deliveries, jobs or workflows are all based on a template, which stores key settings and capabilities. A built-in template is supplied for each component, for which no specific configuration has been defined. You need to configure and adapt templates to your needs and make them available to end-users.


   ![](../assets/do-not-localize/glass.png) Learn how to work with campaign templates in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html)

   ![](../assets/do-not-localize/glass.png) Learn how to configure a workflow template in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html)
   
    ![](../assets/do-not-localize/book.png) Learn more about email templates in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html){target="_blank"}


1. **Configure typology rules**

    Leverage Campaign typologies rules to filter, control and monitor delivery sending. For example, fatigue rules control frequency and quantity of messaging to avoid over-solicitation of recipients. Once implemented, typology rules are referenced in deliveries. 

   Learn more about typologies and fatigue management in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html).

1. **Get familiar with Campaign built-in data model**

    Adobe Campaign comes with a pre-defined data model. To implement and customize your environment, you need to be familiar with the built-in tables of the Adobe Campaign data model and how they relate to each other.

    ![](../assets/do-not-localize/glass.png) [Learn more about Campaign datamodel](../dev/datamodel.md).

## Customize your instance{#implementation-custom-your-instance}

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


## Set up campaign automation{#implementation-automation}

To orchestrate complex marketing campaigns to different audiences across multiple channels, leverage Campaign automation capabilities. 

* Use **workflows** to manage processes and data. Learn more in [this documentation](../../automation/workflow/about-workflows.md)

* Set up **subscription** processes and **landing pages**.  Learn more in [this page](../start/subscriptions.md)

* Configure **typology rules** to define fatigue and control management.  Learn more in [this documentation](../../automation/campaign-opt/campaign-typologies.md)


## Extend your deployment{#implementation-extend}

### Multi-solutions implementation{#implementation-multi-solutions}

If you are using other Adobe solutions, you can connect them to your Campaign environment and combine capabilities.

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Experience Cloud Triggers
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Analytics Data connectors


You can only use Single Sign-On (SSO) to connect to Campaign. Learn more in [this page](connect.md).

![](../assets/do-not-localize/glass.png) Discover the full list of Adobe solution which can be integrated with Adobe Campaign [in this page](../connect/integration.md).

### Connectors{#implementation-connectors}

Connect Campaign with third-party systems to combine a large range of capabilities and automate processes. 

![](../assets/do-not-localize/glass.png) Learn more about available connectors in [this section](../connect/integration.md).

**Connect your CRM to Campaign**

You can connect your Adobe Campaign platform to your CRM third-party systems and synchronize data: contacts, accounts, purchases, etc.  

![](../assets/do-not-localize/glass.png) Learn how to connect your CRM system to Campaign in [this section](../connect/integration.md#gs-crm-connectors)

**Connect to an external database**

You can connect Campaign Cloud database to external systems through the Federated Data Access (FDA) module. 

![](../assets/do-not-localize/glass.png) Learn how to configure Campaign FDA module to define access parameters in [this section](../connect/integration.md#gs-fda)
