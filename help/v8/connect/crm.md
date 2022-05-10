---
title: Work with Campaign and your CRM
description: Learn how to work with Campaign and your CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
---
# Connect your CRM with Campaign {#gs-crm}

Adobe Campaign provides various CRM connectors for linking your Adobe Campaign platform to your third-party systems. These CRM connectors enable you to synchronize contacts, accounts, purchases, etc. They make for easy integration of your application with various third-party and business applications.

These connectors enable quick and easy data integration: Adobe Campaign provides a dedicated assistant for collecting and selecting from the tables available in the CRM. This guarantees two-directional synchronization to make sure data is up-to-date at all times throughout the systems.

Key benefits are:

* Consistent messaging between sales & marketing: the Adobe Campaign integration with your CRM gives both systems access to customer insight and email marketing history allowing all messages to the customer to share the same consistent messaging.

* Holistic view of all prospect and customer data: by integrating Adobe Campaign with your CRM, it is possible to share and access email marketing history on each contact from within the CRM system.

* Activate your CRM data on any channel: with contact data synchronized to Adobe Campaign, communications can be sent on any online or offline channel with Campaign including mobile push, in-app, email, or direct mail.


>[!NOTE]
>
>This feature is available in Adobe Campaign through the **CRM connectors** dedicated package.

## Compatible systems {#compatible-crm-systems-and-limitations}

Supported CRM and versions are detailed in Campaign [Compatibility matrix](../start/compatibility-matrix.md).

>[!CAUTION]
>
> Campaign CRM connectors only work with a secure URL (https).

## Implementation steps {#crm-implementation-steps}

Learn step-by-step procedure to connect Campaign and Microsoft Dynamics in [this page](ac-ms-dyn.md).

Learn step-by-step procedure to connect Campaign and Salesforce.com in [this page](ac-sfdc.md).

Data synchronization between Adobe Campaign and the CRM is carried out via a dedicated workflow activity. Build your workflows to automate synchronization between Campaign and your CRM. You can create a workflow which imports the contacts via Microsoft Dynamics, synchronizes them with the existing Adobe Campaign data, deletes duplicate contacts, and then updates the Adobe Campaign database. Learn more in [this page](crm-data-sync.md).
