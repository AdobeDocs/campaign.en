---
solution: Campaign Classic
product: campaign
title: Implementation guidelines
description: Learn how to implement Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46,4dce4fb0-8aab-4280-ba93-ea11b8e4df8b
---
# Campaign implementation guidelines

In this section, you will learn how to adjust Adobe Campaign to the requirements of your company. Use the following guidelines to structure and organize your implementation. 

1. **Define settings**: grant access, share Client Console, configure channels (email, push, sms)
1. **Prepare your environment**: import profiles, create audiences, design workflow and campaign templates, create typology rules
1. **Customize your instance**: create new data fields, add tables/schemas
1. **Extend your deployment**: connect to Adobe solutions, other products and systems - connectors, multi-solution settings

## Define Campaign settings

### Add users and grant permissions

You can manually add users to Cammaign and associate them with groups, aligned with your role hierarchy. Users will then be able to log in and access the data and permissions which are appropriate for them.

:arrow_upper_right: Learn how to add users to Adobe Campaign in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Install Campaign Client Console

The main user interface of the application is a rich client, in other words, a native application (Windows) that communicates with the Adobe Campaign application server solely with standard internet protocols (SOAP, HTTP, etc.). Adobe Campaign Client Console provides great user-friendliness for productivity, uses very little bandwidth (through the use of a local cache) and is designed for easy deployment. This Console can be deployed from an internet browser, can be updated automatically and does not require any specific network configuration because it only generates HTTP(S) traffic. 

:bulb: [Learn more about Campaign Client Console](connect.md).

## Prepare your environment

Before starting sending messages and creating marketing campaigns, you need to:

1. Import profiles and create audiences

1. Create templates

1. Configure typology rules

1. Get familiar with Campaign built-in data model

## Customize your instance

You can customize many different Campaign areas and capabilities. Most of our customers customize three things:

1. **Tables and schemas**

    Adobe Campaign comes with common schemas to identify data such as: recipients, delivery logs, subscriptions, and more. 
    
    :bulb: Refer to this section to learn more about [Campaign built-in datamodel](../dev/datamodel.md).
    
    :bulb: You can extend existing schemas or create new schemas from scratch. Learn more in [this page](../dev/customize.md).
    
1. **Dashboards and lists**

    You can easily configure lists, add and remove fields and customize columns.
    
    :bulb: Learn how to manage filters and lists in Campaign in [this page](../dev/customize.md#gs-lists-and-filters).

    You can also create new dashboards to display Campaign data depending on your needs. 
    
    :bulb: Learn more in [this page](../dev/customize.md#gs-custom-dashboards).

1. **Reports**

    Campaign provides a set of built-in reports on delivery monitoring, URLs and click streams, tracking, deliverability indicators, and more.

    In addition to built-in reports, Adobe Campaign lets you generate reports in various contexts and to meet different needs. Principles of use and implementation modes are detailed in this document.

    :bulb: Learn more about reporting capabilities in Campaign in [this page](reporting.md).


## Set up campaign automation

To orchestrate complex marketing campaigns to different audiences across multiple channels, leverage Campaign automation capabilities. 

* Workflows: manage processes and data

* Subscriptions and landing pages

* Typology rules: fatigue and control management

* 

## Extend your deployment

### Multi-solutions implementation

You can connect your Campaign instance with Adobe Experience Cloud solutions to combine capabilities.

* Connect to Campaign with an AdobeID
* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Experience Cloud Triggers
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Analytics Data connectors

:bulb: Discover the full list of Adobe solution which can be integrated with Adobe Campaign [in this page](integration.md).

### Connectors

Connect Campaign with third-party systems to combine a large range of capabilities and automate processes. 

:bulb: Learn more about available connectors in [this section](integration.md).

**Connect your CRM to Campaign**

You can connect your Adobe Campaign platform to your CRM third-party systems and synchronize data: contacts, accounts, purchases, etc.  

:bulb: Learn how to connect your CRM system to Campaign in [this section](integration.md#gs-crm-connectors)

**Connect to an external database**

You can connect Campaign Cloud database to external systems through the Federated Data Access (FDA) module. 

:bulb: Learn how to configure Campaign FDA module to define access parameters in [this section](integration.md#gs-fda)

