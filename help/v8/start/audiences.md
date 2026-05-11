---
title: Work with audiences in Campaign
description: Work with audiences in Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/7yA7UY-YeKjSgy6jUpDWdHpCHRuT-FFi4xTfhj3awu8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Work with audiences in Campaign{#gs-ac-audiences}

Profiles represent the contacts stored in your Adobe Campaign database. By default, **recipients** are the primary profiles used when sending deliveries such as emails, SMS, or direct mail. The recipient data stored in the database allows you to define and filter your target audiences, as well as personalize delivery content. In addition to recipients, other profile types exist for specific purposes. For example, seed profiles let you test deliveries before they are sent to your actual audience.

Learn how to import, update and manage profiles and audiences [in this section](../audiences/gs-audiences.md).

## Create lists{#create-lists}

A list is a static set of contacts which can be targeted in delivery actions or updated during an import or another workflow action. For example, a population extracted from the database via a query can be stored as a list.

Learn how to create and manage lists in [this page](../audiences/create-audiences.md).

## Filter the database{#filter-the-database}

Filter configuration lets you select data from a list **[!UICONTROL dynamically]**: when the data is modified, the filtered data is updated. You can create your own filters or use the built-in filters to define a target audience.

Learn how to create and manage filters in [this page](../audiences/create-filters.md).

## Create an audience in a workflow

Targeting can be created via a combination of queries in a graphical sequence in a workflow. You can create audiences which will be targeted according to your requirements. To display the workflow editor, click the **[!UICONTROL Targeting and workflows]** tab in the campaign dashboard.

Learn how to build an audience in a campaign workflow in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"}.


## Active profiles {#active-profiles}

An active profile is a profile that customer has attempted to communicate with during the past 12 months via any channel.

According to your contract, each of your Campaign instances is provisioned with a specific amount of active profiles that are counted for billing purposes. Please refer to your latest contract for reference on number of purchased active profiles. Learn more in [Adobe Campaign product description](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

You can monitor the number of active profiles on your instance directly from Campaign Control Panel. For more on this, refer to the [Control Panel documentation](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.


The following guardrails and limitations apply:

* A profile that has been targeted by several deliveries is counted only once. 
* Profiles targeted in the context of Social marketing on X (Twitter) are not taken into account as active profiles.
* The count is based on the recipient primary key. As a consequence, if a profile is present in two different recipient tables, it can be counted twice as an active profile.

## Privacy and consent{#privacy-and-consent}

Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. Adobe Campaign enables you to collect data, including personal and sensitive information. It is therefore essential that you receive and monitor consent from your recipients.

Learn how to manage privacy and consent in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}.

