---
solution: Campaign Classic
product: campaign
title: Get started with Campaign data model
description: Get started with Campaign data model
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
---
# Get started with Campaign data model{#gs-ac-datamodel}

Adobe Campaign comes with a pre-defined data model. This section gives some details on the built-in tables of the Adobe Campaign data model and their interaction.

To access the description of each table, go to Admin > Configuration > Data schemas, select a resource from the list and click the **Documentation** tab.

Adobe Campaign relies on a Cloud database containing tables that are linked together.

The following diagram shows the joins between the main business tables of the Adobe Campaign data model with the main fields for each.

ADD DIAGRAM

## Built-in profile table {#ootb-profiles}

The built-in recipient table in Adobe Campaign provides a good starting point for building your data model. It has a number of predefined fields and table links that can be easily extended. This is particularly useful when you are mainly targeting recipients, because it fits a simple recipient-centric data model.

The benefits of using the standard recipient table are:

* Working out-of-the-box with key functionalities such as subscriptions, seed lists, and more
* Providing a marketing database with a recipient-centric data model
* Faster implementation
* Easy maintainance by support and partners

It is possible to extend the recipient table, but not to reduce the number of fields or links in the table.

:arrow_upper_right: Learn how to extend the recipient table in the [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

The default recipient schema is **xxl:nmsRecipientXl**.

The corresponding Snowflake table is **PUBLIC.NMSRECIPIENT**
The corresponding delivery logs, tracking logs, etc. are **PUBLIC.XXLBROADLOGRCPXL**, ...
The corresponding target mapping is **mapRecipientXl**
The global source delivery, used as the default source of events which are not related to a delivery, is **globalDeliveryRcpXl**
The default delivery template for email is **mailRcpXl**

You can also use a different recipient table to better fit with your business or functional requirements. This method comes with limitations and is described in [this section](custom-recipient.md).

**See also**

:bulb: Discover how to import profiles in [this section](../start/import.md)
:bulb: Learn more about Campaign audiences in [this section](../start/audiences.md)
