---
solution: Campaign
product: Adobe Campaign
title: Work with Campaign and your CRM
description: Learn how to work with Campaign and your CRM 
feature: Overview
role: Data Engineer
level: Beginner
---
# Connect your CRM with Campaign {#gs-crm}

Adobe Campaign provides various CRM connectors for linking your Adobe Campaign platform to your third-party systems. These CRM connectors enable you to synchronize contacts, accounts, purchases, etc. They make for easy integration of your application with various third-party and business applications.

These connectors enable quick and easy data integration: Adobe Campaign provides a dedicated assistant for collecting and selecting from the tables available in the CRM. This guarantees two-directional synchronization to make sure data is up-to-date at all times throughout the systems.

>[!NOTE]
>
>This feature is available in Adobe Campaign through the **CRM connectors** dedicated package.

## Compatible systems {#compatible-crm-systems-and-limitations}

Supported CRM and versions are detailed in Campaign [Compatibility matrix](../start/compatibility-matrix.md).

**NOTE** - The CRM connectors only work with a secure URL (https).

## Implementation steps {#crm-implementation-steps}

:arrow_upper_right: Learn step-by-step procedure to connect Campaign and Microsoft Dynamics in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

:arrow_upper_right: Learn step-by-step procedure to connect Campaign and Salesforce in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


Data synchronization between Adobe Campaign and the CRM is carried out via a dedicated workflow activity. Build your workflows to automate synchronization between Campaign and your CRM. You can create a workflow which imports the contacts via Microsoft Dynamics, synchronizes them with the existing Adobe Campaign data, deletes duplicate contacts, and then updates the Adobe Campaign database.

:arrow_upper_right: Learn more in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

