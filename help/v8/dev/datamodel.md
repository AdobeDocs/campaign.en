---
solution: Campaign Classic
product: campaign
title: Get started with Campaign data model
description: Get started with Campaign data model
feature: Overview
role: Data Engineer
level: Beginner
exl-id: b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
---
# Get started with Campaign data model{#gs-ac-datamodel}

## Basics

TO DO

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


See also:

* Discover how to import profiles in [this section](../start/import.md)
* Learn more about Campaign audiences in [this section](../start/audiences.md)
