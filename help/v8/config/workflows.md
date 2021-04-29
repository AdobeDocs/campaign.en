---
solution: Campaign Classic
product: campaign
title: Get started with campaign automation
description: Get started with campaign automation
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
---
# Manage and automate processes

Configure Campaign to leverage powerful marketing campaign automation capabilities.

You can set up:

* Workflows
* Recurring campaigns
* End-to-end validation cycle
* Alerts
* Automatic report sending
* Triggered events

## Design and use workflows{#gs-ac-wf}

Use Adobe Campaign workflows to improve the speed and scale of every aspect of your marketing campaigns, from creating segments and preparing messages to delivery.

Learn more about workflows in these sections:

* [Get started with worflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Workflow activities
    * [Targeting activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html): query, read list, enrichment, union, and more
    * [Flow control activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html): scheduler, fork, alert, external signal, and more
    * [Action activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): cross-channel deliveries, Javascript code, CRM activities, update aggregate, and more
    * [Event activities](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html): file transfer, web download and more
* [Learn through end-to-end use cases](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Build an audience in a marketing campaign workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Workflow best practices](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Built-in technical workfows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Monitor workflows execution](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Set up recurring campaigns

Design recurring and create a new delivery instance each time it executes. For example, if your workflow is designed to run once a week, that would result in 52 Deliveries after one year. This also means that logs will be separated by each delivery instance.

:arrow_upper_right: Learn how to create a recurring campaign in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).

## Configure your end-to-end validation cycle

Set up approval process for each step of your deliveries and ensure full monitoring and control of the various processes of your marketing campaigns: targeting, content, budget, extraction, and sending a proof.

Notifications are sent to the Adobe Campaign operators who are set as reviewers to inform them of an approval request.

:arrow_upper_right: Learn how to set up and manage the approval process in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html).


## Send alerts

As a Campaign operator, you can receive alerts when a faiure happens.

You can create a workflow that will let you monitor the status of a set of workflows and send recurring messages to supervisors.

:arrow_upper_right: Learn how to create a workflow to monitor the status of other workflows in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow).

You can also receive an alert when a failure happens

## Send automatic reports

:arrow_upper_right: Learn how to automatically send a report to a list of operators [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list).


## Leverage trigger events

Use Campaign Transactional messaging to automate messages generated from events triggered from information systems. These transactional messages can be invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement or website account creation for instance. These messages can be sent individually or in batch via email, SMS or push notificat)ions.

:arrow_upper_right: Learn more about transactional messaging capabilities in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Connect Adobe Campaign and Adobe Analytics to retrieve user actions and send near real-time personalized messages. 

:arrow_upper_right: Learn how to integrate Campaign with Analytics triggers in [this guide](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud).


:bulb: Learn how to integrate Campaign with other solutions in [this section](../start/connect.md)
