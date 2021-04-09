---
solution: Campaign Classic
product: campaign
title: Get started with audiences
description: Get started with audiences
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
---
# Get Started with audiences{#gs-ac-audiences}

Profiles can be grouped in lists or collected by querying the database.

## Work with profiles{#gs-ac-profiles}

Profiles are centralized in the cloud database. There are many possible mechanisms for acquiring profiles and building up this database: on-line collection via web forms, manual or automatic import of text files, replication with company databases or other information systems. With Adobe Campaign, you can incorporate marketing history, purchase information, preferences, CRM data, and any relevant PI data in a consolidated view to analyze and take action.

“**Profile**” means a record of information representing an end-customer, prospect, or lead. 
A record in the **xxl:nmsRecipientXl** table or an external table contains a cookie ID, Customer ID, mobile identifier or other information relevant to a particular channel. Learn more about built-in profiles and recipient tables in [this section](#ootb-profiles).

In Adobe Campaign, recipients are the default profiles targeted for sending deliveries (emails, SMS, etc.). Recipient data stored in the database enable you to filter the target that will receive any given delivery and to add personalization data in your delivery contents. Other types of profiles exist in the database. They are designed for different uses. For example, seed profiles are made to test your deliveries before they are sent to the final target.

![](assets/do-not-localize/how-to-video.png) [Understand the concept of profiles in video](#create-profiles-video)

Learn how to manage profiles in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html).

## Create lists

A list is a static set of profiles that can be targeted in delivery actions or updated during import operations or during workflow execution. For example, a population extracted from the database via a query can supply a list.

Learn more about lists and how to create and manage them in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Query the database

Use the **Query** activity in a workflow to query your database, segment data and build complex audiences. 

Learn more about Campaign queries in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

All targeting activities are listed in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## Create an audience in a  workflow

Learn how to build an audience in a campaign workflow in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

**What's next?**

* [Design and execute a campaign-specific workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

* [Learn how to select the audience of a campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

* [Get started with workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
