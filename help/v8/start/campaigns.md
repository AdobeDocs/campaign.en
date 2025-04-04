---
title: Get Started with Campaigns
description: Get started with campaigns
feature: Cross Channel Orchestration
role: User
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66
---
# Get started with campaigns {#gs-ac-campaigns}

Adobe Campaign offers a set of solutions that help you personalize and deliver campaigns across all of your online and offline channels. You can create, configure, execute and analyze marketing campaigns. All marketing campaigns can be managed from a unified control center. Discover how to browse and create marketing campaigns in this section.

Campaigns include actions (deliveries) and processes (importing or extracting files), as well as resources (marketing documents, delivery outlines). They are used in marketing campaigns. Campaigns are part of a program, and programs are included in a campaign plan.

## Cross-channel campaign orchestration{#cross-channel-orchestration}

Adobe Campaign lets you design and orchestrate targeted and personalized campaigns on multiple channels: email, direct mail, SMS, push notification. A single interface provides you with all the functions required to schedule, orchestrate, configure, personalize, automate, execute, and measure all your campaigns and communications.

![](assets/campaign-tab.png) 

### Core concepts{#ac-core-concepts}

Before starting implementing marketing campaigns, you need to be familiar with the following concepts:

* **Marketing campaign**: a campaign centralizes all the elements related to a marketing campaign: deliveries, targeting rules, costs, export files, related documents, etc. Each campaign is attached to a program.

* **Program**: a program lets you define marketing actions for a calendar period: launch, canvassing, loyalty, etc. Each program contains campaigns linked to a calendar, which provides an overall view.

* **Plan**: the marketing plan can contain multiple programs. It is linked to a calendar period, has an allocated budget and can also be linked up to documents and objectives.

* **Campaign workflow**: a campaign workflow contains activities to build the campaign logic. Use campaign workflows to define audiences and create deliveries for all available channels.

* **Recurring campaigns**: recurring campaigns are created from a specific template defining the workflow template to be executed and the execution schedule.

* **Periodic campaigns**: a periodic campaign is a campaign created automatically according to the execution schedule of its template.

## Marketing campaign workspace{#ac-workspace}

Adobe Campaign lets you create, configure, execute and analyze all marketing campaigns from a unified control center.

![](assets/calendar.png) 

Discover how to access and implement marketing campaigns in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html){target="_blank"}.

## Key steps to start{#gs-ac-start}

Key steps to create a cross-channel marketing campaign are:

1. **Plan and design marketing programs and campaigns**

    Define hierarchy and schedule, set budget, add resources, select operators. 
    
   Learn how to create a marketing plan and configure campaigns in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-create.html){target="_blank"}.

    All marketing campaigns are based on a template, which stores main settings and capabilities. A built-in template is supplied in order to create a campaign for which no specific configuration has been defined. You can create and configure your campaign templates and then create campaigns from these templates.

   Learn how to work with campaign templates in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html){target="_blank"}.

   Discover recurring campaigns and how to configure them in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html){target="_blank"}.

1. **Define audiences**
    
    You can build the audience in a workflow or select an existing group, such as a recipient list, subscribers of a newsletter, recipients of a previous delivery, or any filtering condition.

    ![](assets/campaign-wf.png) 
    
    Learn how to define the audience of your messages in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html){target="_blank"}.
    
1. **Create deliveries**

    Select channel(s), define the message content and start deliveries.

    ![](assets/campaign-dashboard.png) 
    
    Learn how to create and start marketing campaign deliveries in [this page](../../automation/campaigns/marketing-campaign-deliveries.md).

    You can associate various documents with a campaign: report, photo, web page, diagram, etc. Learn more about associated documents in [this page](../../automation/campaigns/marketing-campaign-assets.md).
    
1. **Set up the approval process**

    Adobe Campaign lets you set up collaborative approval processes for the main stages of the marketing campaign. For each campaign you can approve the delivery target, content, and costs. Adobe Campaign operators in charge of approval can be notified by email and can accept or reject approval from the console or via a web connection. 

   Learn how to set up and manage approvals in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html#campaign-orchestration){target="_blank"}.


## Distributed Marketing add-on{#distributed-marketing-add-on}

Adobe Campaign offers a **Distributed Marketing** add-on for implementing cooperative campaigns between central entities (headquarters, marketing departments, etc.) and local entities (stores, regional agencies, etc.). This cooperation is based on a shared workspace known as the **[!UICONTROL List of campaign packages]**, where campaign templates designed by central entities are offered to local entities.

>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Learn how to configure and use Campaign Distributed Marketing capabilities in [this page](https://experienceleague.adobe.com/docs/campaign/automation/distributed-marketing/about-distributed-marketing.html){target="_blank"}.

## Response Management add-on{#response-manager-add-on} 

Adobe Campaign offers a **Response Management** add-on that lets you measure the success and profitability of marketing campaigns or offer propositions across communication channels: email, mobile, direct mail, etc.

>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

[](../assets/do-not-localize/book.png) Learn how to configure and use Campaign Response Manager in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/response-manager/about-response-manager.html){target="_blank"}.
