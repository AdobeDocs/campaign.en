---
solution: Campaign Classic
product: campaign
title: Implementation guidelines
description: Learn how to implement Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
---

# Campaign v8 implementation guidelines

In this section, you will learn how to adjust Adobe Campaign to the requirements of your company. Use the following guidelines to structure and organize your implementation. 

1. **Define settings**: grant access, share client console, configure channels (email, push, sms)
1. **Prepare your environment**: import profiles, create audiences, design workflow and campaign templates, create typology rules, 
1. **Customize your instance**: create new data fields, add tables/schemas
1. **Extend your deployment**: connect to Adobe solutions, other products and systems - connectors, multi-solution settings

## Define Campaign settings

### Add users and grant permissions

You can manually add users to Cammaign and associate them with groups, aligned with your role hierarchy. Users will then be able to log in and access the data and permilssions which are appropriate for them.

Learn how to add users to Adobe Campaign in this section.

### Install Campaign Client Console

The main user interface of the application is a rich client, in other words, a native application (Windows) that communicates with the Adobe Campaign application server solely with standard internet protocols (SOAP, HTTP, etc.). Adobe Campaign Client Console provides great user-friendliness for productivity, uses very little bandwidth (through the use of a local cache) and is designed for easy deployment. This console can be deployed from an internet browser, can be updated automatically and does not require any specific network configuration because it only generates HTTP(S) traffic. [Learn more about Campaign Client Console](connect.md).

## Prepare your environment

## Customize your instance

You can customize many different Campaign areas and capabilities. Most of our customers customize three things:

1. **Tables and schemas**

    Adobe Campaign comes with common schemas to identify data such as: recipients, delivery logs, subscriptions, and more. Refer to this section to learn more about Campaign built-in datamodel.
    
    You can extend existing schemas or create new schemas from scratch. Learn more in this page.
    
1. **Dashboards and lists**

    You can easily configure lists, add and remove fields and customize columns. Learn more.

    You can also create new dashboard depending on your needs. Learn more.

1. **Reports**

    Campaign provides a set of built-in reports on delivery monitoring, URLs and click streams, tracking, deliverability indicators, and more.

    In addition to built-in reports, Adobe Campaign lets you generate reports in various contexts and to meet different needs. Principles of use and implementation modes are detailed in this document.


## Extend your deployment

### Multi-solutions implementation

Discover the full list of Adobe solution which can be integrated with Adobe Campaign in this page. 

* Connect to Campaign with an AdobeID
* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Experience Cloud Triggers
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Analytics Data connectors

### Connectors

You can connect Campaign with third-party systems to combine a large range of capabilities. Learn more in [this section](integration.md).

**Connect your CRM to Campaign**

You can connect your Adobe Campaign platform to your CRM third-party systems and synchronize data: contacts, accounts, purchases, etc.  Learn how to connect your CRM system to Campaign in [this section](integration.md#gs-crm-connectors)

**Connect to an external database**

You can connect Campaign Cloud database to external systems. Learn how to configure Campaign FDA module to define access parameters in [this section](integration.md#gs-fda)


