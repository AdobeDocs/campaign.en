---
title: Get started with Campaign data model
description: Get started with Campaign data model
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
---
# Get started with Campaign data model{#gs-ac-datamodel}

Adobe Campaign comes with a pre-defined data model. This section gives some details on the built-in tables of the Adobe Campaign data model and their interaction. Adobe Campaign relies on a Cloud database containing tables that are linked together.

The basic structure of the Adobe Campaign data model can be described as follows:

* **Recipient table**: The data model relies on a main table which is by default the Recipient table (nmsRecipient). This table stores all the marketing profiles.

    ![](../assets/do-not-localize/glass.png) For more on the Recipient table, see [this section](#ootb-profiles).

* **Delivery table**: The data model also includes a part dedicated to store all the marketing activities. Usually it is the Delivery table (NmsDelivery). Each record in this table represents a delivery action or a delivery template. It contains all the necessary parameters for performing deliveries such as target, content, etc.

* **Logs tables**: These tables store all the logs associated with the execution of the campaigns.

    Delivery logs are all messages sent to recipients or devices across all channels. The main Delivery logs table (NmsBroadLogRcp) contains the delivery logs for all recipients.
    The main Tracking logs table (NmsTrackingLogRcp) stores the tracking logs for all recipients. The tracking logs refer to reactions of recipients, such as email openings and clicks. Each reaction corresponds to a tracking log.
    Delivery logs and tracking logs are deleted after a certain period, which is specified in Adobe Campaign and can be modified. Therefore, it is highly recommended to export the logs on a regular basis.

* **Technical tables**: Gather technical data used for the applicative process, including operators and user rights (xtkGroup), folders (XtkFolder).

>[!NOTE]
>
>To access the description of each table, go to Admin > Configuration > Data schemas, select a resource from the list and click the **Documentation** tab.

When starting with Adobe Campaign, you need to assess the default data model to check which table is the best suited to store your marketing data.

You can use the default Recipient table with the out-of-the-box fields, such as described in [this section](#ootb-profiles). If needed, you can extend it with two mechanisms:

* [Extend an existing table](extend-schema.md) with new fields. For example, you can add a new “Loyalty” field to the Recipient table.
* [Create a new table](create-schema.md), for example a “Purchase” table listing all the purchases made by each profile of the database, and link it to the Recipient table.

![](../assets/do-not-localize/glass.png) Discover best practices when working with Campaign datamodel in [this section](datamodel-best-practices.md).

## Built-in profile table {#ootb-profiles}

The built-in recipient table (nmsrecipient) in Adobe Campaign provides a good starting point for building your data model. It has a number of pre-defined fields and table links that can be easily extended. This is particularly useful when you are mainly targeting recipients, because it fits a simple recipient-centric data model.

The benefits of using the standard recipient table are:

* Working out-of-the-box with key functionalities such as subscriptions, seed lists, and more
* Providing a marketing database with a recipient-centric data model
* Faster implementation
* Easy maintainance by support and partners

It is possible to extend the recipient table, but not to reduce the number of fields or links in the table.

![](../assets/do-not-localize/glass.png) Learn how to extend an existing schema in [this section](extend-schema.md).

![](../assets/do-not-localize/book.png) Discover examples of built-in recipient table extensions in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target="_blank"}

You can also use a different recipient table to better fit with your business or functional requirements. This method comes with limitations and is described in [this section](custom-recipient.md).

## Campaign tables and Cloud database

For a better understanding of table management in Campaign v8, note that, in the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), tables are replicated between Campaign and its Snowflake Cloud database.

![](../assets/do-not-localize/glass.png) Learn more about replication strategy and mechanisms in [this section](../architecture/replication.md).

**Related topics**

![](../assets/do-not-localize/glass.png) Discover how to import profiles in [this section](../start/import.md)
![](../assets/do-not-localize/glass.png) Learn more about Campaign audiences in [this section](../start/audiences.md)
