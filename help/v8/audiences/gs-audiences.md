---
title: Get started with profiles and audiences in Campaign
description: Learn how to create and manage profiles and audiences in Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
---
# Get started with profiles and audiences in Campaign{#gs-profiles-and-audiences}

Profiles are contacts stored in Campaign database, such as customers, subscribers to a service or prospects. There are many possible mechanisms for acquiring profiles and building up this database: on-line collection via web forms, manual or automatic import of text files, replication with company databases or other information systems. With Adobe Campaign, you can incorporate marketing history, purchase information, preferences, CRM data, and any relevant PI data in a consolidated view to analyze and take action. Profiles contain all the information required for targeting, qualifying and tracking individuals.

A profile is a record in the **nmsRecipient** table or an external table which stores all the profile attributes, such as first name, last name, email address, a cookie ID, Customer ID, mobile identifier or other information relevant to a particular channel. Other tables linked to the recipient table contain profile-related data, for example the delivery logs table which contains records of all deliveries sent to recipients. Learn more about built-in profiles and recipient tables in [this section](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign, **recipients** are the default profiles targeted for sending deliveries (emails, SMS, etc.). Recipient data stored in the database enable you to filter the target that will receive any given delivery and to add personalization data in your delivery contents. Other types of profiles exist in the database. They are designed for different uses. For example, seed profiles are made to test your deliveries before they are sent to the final target.


To populate Adobe Campaign with profile data, you can:

* [import data files](import.md) from an external data source such as a CRM system
* [create web forms](../dev/webapps.md) to allow customers to enter their own information and create their own profile
* [map to an external database](../connect/fda.md) where profiles are stored
* enter profiles manually in the Client console, as below:

![](assets/create-profile.png) 

You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).
