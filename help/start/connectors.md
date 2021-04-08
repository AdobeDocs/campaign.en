---
solution: Campaign Classic
product: campaign
title: Get started with connectors
description: Get started with connectors
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 540ac251-b873-4402-8bc5-f9ad849b2363
---
# Connect Campaign and external systems {#gs-ac-connectors}

Adobe Campaign comes with several connectors that allow you to communicate with external applications, connect to database engines, share and synchronize data.

Check compatible systems and versions in [this page](compatibility-matrix.md).

## CRM Connectors{#gs-crm-connectors}

You can connect your Adobe Campaign platform to your CRM third-party systems and synchronize data: contacts, accounts, purchases, etc. 

Activate your CRM data on cross-channel communication: learn how to pass on contacts from your CRM system to Adobe Campaign, and share campaign data back from Adobe Campaign to your CRM system.
CRM connectors enable quick and easy data integration: Adobe Campaign provides a dedicated wizard for collecting and selecting from the tables available in the CRM. This guarantees two-directional synchronization to make sure data is up-to-date at all times throughout the systems.

Learn how to integrate Campaign with Microsoft Dynamics 365 and Salesforce.com in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-connectors.html).


## Federated Data Access (FDA){#gs-fda}

Use the FDA Connector (Federated Data Access) to connect Campaign to one or more external databases and process information stored into them without affecting your Campaign Cloud Database data. you can access external data without changing the structure of Adobe Campaign data.

Campaign FDA option allows you to extend your data model in a third-party database. It will automatically detect the structure of the targeted tables and use data from the SQL sources.

Learn how to **connect Campaign** to an external database in [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/configure-fda/config-databases/configure-fda.html)

Specific **permissions** are required on the external database to work with Campaign. [Learn more](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/configure-fda/remote-database-access-rights.html)

Once the data schema is created, data can be processed in Adobe Campaign workflows. For more on this, refer to [this section](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/accessing-an-external-database--fda-.html).
