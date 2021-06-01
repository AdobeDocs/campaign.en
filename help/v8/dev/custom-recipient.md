---
product: Adobe Campaign
title: Change your default recipient table
description: Learn how to use a custom recipient table
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
---
# Use a custom recipient table{#gs-ac-custom-recipient}

Adobe Campaign comes with a built-in profile table: **nmsRecipient**. This table has a number of predefined fields and tables that can be easily extended. Learn more about this table in [this page](datamodel.md#ootb-profiles).

Built-in table extension offers flexibility, but it does not allow to remove some unused fields or links. As a consequence, using a custom recipient table can be a good option when your datamodel differs drastically from Campaign built-in recipient table structure, or if you have a large number of profiles.  However, this method requires certain precautions when implementing it.

This functionality allows Adobe Campaign to process data from an external database: this data will be used as a set of profiles for deliveries. Implementing this process involves limitations, such as:

* No update stream to and from Campaign Cloud database: data from this table can be updated directly via the database engine that hosts it.
* Processes operating on the existing database need to be stable.
* Using a profile database with a non-standard structure: possibility of delivering to profiles saved in various tables with various structures, using a single instance.

This section describes the key points to map existing tables in Adobe Campaign and the configuration settings to apply to execute deliveries based on any table. It also describes how to design querying interfaces for end-users. 

>[!CAUTION]
>
>Adobe Campaign customization is reserved to expert users only. It requires expertise in input form and schema design.

