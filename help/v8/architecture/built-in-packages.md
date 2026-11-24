---
title: Built-in packages
description: Learn what built-in packages are in Campaign v8, how they differ from custom data packages, and which ones are available
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
---
# Built-in packages {#built-in-packages}

Built-in packages (also known as standard packages) contain the features of Adobe Campaign. In Campaign v8, Adobe installs and manages these packages for you. You do not need to install them.

## Built-in packages and custom packages {#built-in-vs-custom}

Campaign uses two kinds of packages. Make sure you work with the right one.

| | Built-in packages | Custom packages |
|---|---|---|
| Purpose | Provide the Campaign features, such as channels, integrations, and add-ons. | Export and import your own configuration and data, for example from a staging to a production environment. |
| Who manages them | Adobe installs and manages them. With Managed Cloud Services, you cannot modify installed built-in packages. | You create, export, and import them. |
| Where to learn more | This page. | [Work with data packages](../dev/packages.md) |

## Check the installed packages {#check-installed-packages}

To check which built-in packages are installed on your instance, browse to **[!UICONTROL Administration > Configuration > Package management > Installed packages]**. You can also view them in the Instance monitoring of the Control Panel. Learn more in [Campaign monitoring overview](../start/monitor.md#monitor-instance).

If you need a package or add-on that was not provisioned for you, contact Adobe Customer Care or your Adobe Transition Manager.

## List of built-in packages {#list-of-built-in-packages}

The following table lists the built-in packages for information. The availability of each package is subject to your license agreement and your deployment model.

| Package | Description |
|---|---|
| Delivery | Mandatory core package of Adobe Campaign. It lets you send deliveries. [Learn more](../start/gs-message.md) |
| Marketing campaigns (Campaign) | Defines, optimizes, executes, and analyzes communications and marketing campaigns. [Learn more](../start/campaigns.md) |
| Marketing resources (MRM) | Controls marketing actions in a collaborative mode, with management and tracking of tasks, budgets, and marketing resources. [Learn more](../../automation/mrm/about-marketing-resource-management.md) |
| Offer engine (interaction) | Responds in real time during an interaction with a contact by making one or several adapted offers. [Learn more](../interaction/interaction.md) |
| Social networks (Social Marketing) | Synchronizes Adobe Campaign with X (formerly Twitter). [Learn more](../connect/ac-tw.md) |
| Transactional message control and execution (Message Center) | Manages trigger messages generated from events in information systems, with higher availability and better load management. [Learn more](../send/transactional.md) |
| LINE channel | Sends deliveries through the LINE channel. [Learn more](../send/line/line.md) |
| Direct Mail channel | Sends deliveries through the direct mail channel. [Learn more](../send/direct-mail.md) |
| Mobile channel (SMS) | Sends deliveries through the mobile channel (SMS), including the SMS connector v2 (generally available since 8.9.1). [Learn more](../send/sms/sms.md) |
| Mobile App Channel | Sends personalized notifications to iOS and Android devices through apps. [Learn more](../send/push.md) |
| Content Manager | Creates recurring newsletters or websites, then validates and publishes your messages. [Learn more](../../automation/workflow/content-management.md) |
| Online surveys (Survey Manager) | Creates and manages online forms to add or modify profile information, subscribe, unsubscribe, or enter a competition. [Learn more](../dev/surveys/about-surveys.md) |
| Marketing Analytics | Analyzes and measures data, calculates statistics, and simplifies report creation. [Learn more](../reporting/gs-reporting.md) |
| Response Manager | Measures the success and profitability of marketing campaigns or offers across all channels. [Learn more](../../automation/response/about-response-manager.md) |
| Access to external data (Federated Data Access) | Processes information stored in external databases without changing the structure of Adobe Campaign data. [Learn more](../connect/fda.md) |
| Campaign Optimization | Controls, filters, and monitors deliveries so that messages meet customer needs and company communication policies. [Learn more](../../automation/campaign-opt/campaign-typologies.md) |
| Deliverability monitoring (Email Deliverability) | Measures whether your messages reach the inbox without bouncing or being marked as spam. [Learn more](../send/monitoring-deliverability.md) |
| Coupon Management | Creates sets of coupons to add to marketing offers. [Learn more](../send/personalized-coupons.md) |
| Inbox Rendering (IR) | Previews messages in the contexts in which they may be received and checks compatibility with major desktop and web email clients. [Learn more](../send/inbox-rendering.md) |
| Central/local Marketing (Distributed Marketing) | Implements cooperative campaigns between central entities, such as headquarters, and local entities, such as sales points. [Learn more](../../automation/distributed-marketing/about-distributed-marketing.md) |
| CRM connectors | Links Adobe Campaign to third-party CRM systems. [Learn more](../connect/crm.md) |
| Web Analytics connectors | Allows Adobe Campaign and Adobe Analytics to interact. [Learn more](../connect/ac-aa.md) |
| AEM integration | Manages the content of emails and forms in Adobe Experience Manager. [Learn more](../connect/ac-aem.md) |
| Adobe Experience Cloud Shared Audiences Integration | Exchanges and shares audiences with [!DNL Adobe CX Enterprise] (formerly Adobe Experience Cloud) solutions and apps. [Learn more](../start/shared-audiences.md) |
| Integration with Adobe Experience Cloud | Imports and exports audiences from [!DNL Adobe CX Enterprise] (formerly Adobe Experience Cloud) solutions into Adobe Campaign. [Learn more](../connect/integration.md) |
| Privacy Data Protection Regulation | Adds functionality to help with privacy compliance. [Learn more](../start/privacy.md) |
| AMP support | Sends dynamic emails with the interactive AMP for email format. [Learn more](../send/defining-interactive-content.md) |


>[!NOTE]
>
>The Marketing resources (MRM), Coupon Management, and Online surveys packages are not available in the context of an Enterprise (FFDA) deployment of Campaign. Learn more in [Feature availability](../architecture/enterprise-deployment.md#feature-availability).

## Related topics {#related-topics}

* [Work with data packages](../dev/packages.md): create, export, and import your own custom packages.
* [Technical workflows](../../automation/workflow/technical-workflows.md): the built-in technical workflows and the package that installs each of them.
* [Feature availability in FFDA deployments](enterprise-deployment.md#feature-availability): the capabilities that are not available in Enterprise (FFDA) deployments.
* [Unsupported features](../start/v7-to-v8.md#gs-removed): the Campaign Classic v7 capabilities that are no longer supported in v8.
* [Global principles](general-architecture.md): what you can and cannot modify in a Managed Cloud Services environment.
* [Get started with Campaign v8](../start/get-started.md): an overview of the core capabilities and add-ons.
