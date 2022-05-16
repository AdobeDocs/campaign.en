---
title: Work with audiences in Campaign
description: Work with audiences in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
---
# Work with audiences in Campaign{#gs-ac-audiences}

Profiles are contacts stored in Campaign database. 

In Adobe Campaign, **recipients** are the default profiles targeted for sending deliveries (emails, SMS, etc.). Recipient data stored in the database enable you to filter the target that will receive any given delivery and to add personalization data in your delivery contents. Other types of profiles exist in the database. They are designed for different uses. For example, seed profiles are made to test your deliveries before they are sent to the final target.

Learn how to import, update and manage profiles and audiences [in this section](../audiences/gs-audiences.md).

## Create lists{#create-lists}

A list is a static set of contacts which can be targeted in delivery actions or updated during an import or another workflow action. For example, a population extracted from the database via a query can be stored as a list.

![](../assets/do-not-localize/glass.png) Learn how to create and manage lists in [this page](../audiences/create-audiences.md).

## Filter the database{#filter-the-database}

Filter configuration lets you select data from a list **[!UICONTROL dynamically]**: when the data is modified, the filtered data is updated. You can create your own filters or use the built-in filters to define a target audience.

![](../assets/do-not-localize/glass.png) Learn how to create and manage filters in [this page](../audiences/create-filters.md).

## Create an audience in a workflow

Targeting can be created via a combination of queries in a graphical sequence in a workflow. You can create audiences which will be targeted according to your requirements. To display the workflow editor, click the **[!UICONTROL Targeting and workflows]** tab in the campaign dashboard.

![](../assets/do-not-localize/book.png) Learn how to build an audience in a campaign workflow in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target="_blank"}.


## Active profiles{#active-profiles}

According to your contract, each of your Campaign instances is provisioned with a specific number of active profiles that are counted for billing purposes. Please refer to your latest contract for reference on number of purchased active profiles.

**Profile** means a record of information (e.g.: a record in the [Recipient table](../dev/datamodel.md) or an external table containing a cookie ID, Customer ID, mobile identifier or other information relevant to a particular channel) representing an end-customer, prospect, or lead. Profiles are considered active if they have been targeted or communicated within the past 12 months via any channel.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## Privacy and consent{#privacy-and-consent}

Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. Adobe Campaign enables you to collect data, including personal and sensitive information. It is therefore essential that you receive and monitor consent from your recipients.

![](../assets/do-not-localize/book.png) Learn how to manage privacy and consent in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}.

**Related topics** in Campaign Classic v7 documentation:

* [Design and execute a campaign-specific workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target="_blank"}

* [Learn how to select the audience of a campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target="_blank"}

* [Get started with workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target="_blank"}
