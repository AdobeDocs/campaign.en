---
solution: Campaign v8
product: campaign
title: Get started with profiles
description: Get started with profiles
feature: Profiles
role: Data Engineer
level: Beginner
---

# Get Started with profiles{#gs-ac-profiles}

Profiles are centralized in the cloud database. There are many possible mechanisms for acquiring profiles and building up this database: on-line collection via web forms, manual or automatic import of text files, replication with company databases or other information systems. With Adobe Campaign, you can incorporate marketing history, purchase information, preferences, CRM data, and any relevant PI data in a consolidated view to analyze and take action.

“**Profile**” means a record of information representing an end-customer, prospect, or lead. 
A record in the **xxl:nmsRecipientXl** table or an external table contains a cookie ID, Customer ID, mobile identifier or other information relevant to a particular channel. Learn more about built-in profiles and recipient tables in [this section](#ootb-profiles).

In Adobe Campaign, recipients are the default profiles targeted for sending deliveries (emails, SMS, etc.). Recipient data stored in the database enable you to filter the target that will receive any given delivery and to add personalization data in your delivery contents. Other types of profiles exist in the database. They are designed for different uses. For example, seed profiles are made to test your deliveries before they are sent to the final target.

![](assets/do-not-localize/how-to-video.png) [Understand the concept of profiles in video](#create-profiles-video)

Learn how to manage profiles in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html).

## Built-in profile table {#ootb-profiles}

The built-in Recipient table in Adobe Campaign provides a good starting point for building your data model. It has a number of predefined fields and table links that can be easily extended. This is particularly useful when you are mainly targeting recipients, because it fits a simple recipient-centric data model.

The benefits of using the standard Recipient table are as follows:

* Working out-of-the-box with functionalities such as subscriptions, seed lists, surveys, social, and so on.
* Providing a marketing database with a recipient-centric data model.
Faster implementation.
* Easy maintainance by support and partners.

It is possible to extend the Recipient table, but not to reduce the number of fields or links in the table.

The default recipient schema is **xxl:nmsRecipientXl**

The corresponding Snowflake table is **PUBLIC.NMSRECIPIENT**
The corresponding delivery logs, tracking logs, etc. are **PUBLIC.XXLBROADLOGRCPXL**, ...
The corresponding target mapping is **mapRecipientXl**
The global source delivery, used as the default source of events which are not related to a delivery, is **globalDeliveryRcpXl**
The default delivery template for email is **mailRcpXl**

Learn more about Campaign data model in [this section](datamodel.md)

## Add profiles to Campaign

You can use workflows to import or export recipients profiles into Adobe Campaign database, or set up generic imports or export jobs. You can also use web applications to feed your database.

### Import profiles in a workflow

Profile imports are configured in dedicated templates executed through workflows via the **Import** activity. They can be repeated automatically according to a schedule, for example to automate data exchange between several information systems. Learn more in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html).

You can also run unitary import jobs to feed your database. Learn more in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html).

See also:
* [Get started with imports and exports](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

* [Import and export best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

* [Configure and execute an import](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

### Run unitary imports

DETAILS TO ADD + LINK

### Collect profiles through web apps

DETAILS TO ADD + LINK
