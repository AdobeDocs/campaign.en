---
title: Campaign versions and upgrades
description: Learn more about Campaign versions and upgrades
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
TQID: https://experienceleague.adobe.com/EaoWEmt7vNplA6Cs6CdMvP-iwia6BkaDRjawsPoa6fs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Versions and upgrades {#upgrades}

Adobe Campaign v8 is offered exclusively as a **Managed Cloud Services** solution. Adobe manages and performs every server-side upgrade for you — there is no on-premises or hybrid deployment of v8, and no server upgrade to schedule or perform yourself.

Adobe Campaign is regularly updated. This regular frequency of updates aims at getting the latest and greatest in your hands, keeping your environment secure, and improving your experience with our product.

As a Managed Cloud Services user:

* Your Campaign server instance is upgraded by Adobe with every new version, automatically and without requiring any action on your part.
* Your Adobe representative contacts you ahead of an upgrade that affects your environment.
* **Your client console is the one component you are responsible for keeping current.** It must be upgraded to the same version as your Campaign server. Learn how to upgrade your client console in [this page](../start/connect.md#upgrade-ac-console).

In addition, as a customer, ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).

>[!IMPORTANT]
>
>Adobe reserves the right to apply critical security patches to your hosted environment at any time, without prior notice, in order to remediate vulnerabilities as quickly as possible. These patches are deployed without service interruption. Remediating a critical vulnerability takes precedence over advance notification.

## Campaign versions {#versions}

Adobe Campaign periodically releases product versions which improve the performance, security, logic, and usability of your Campaign infrastructure.

These upgrades can be:

* **Major upgrades**, from a major version to another, for example from v7 to v8. These upgrades bring new capabilities, improvements, compatibility and security updates, and fixes.
* **Minor upgrades**, from a minor version to another, for example from v8.5 to v8.6. These upgrades bring improvements, compatibility and security updates, and fixes.
* **Patch upgrades**, from a patch version to another, for example from v8.5.1 to v8.5.2. These upgrades bring security updates and fixes.

Detailed information about each new version is available in the [Release notes](release-notes.md). Security-related fixes are called out within each release's notes — see [How can I be informed of the release of a new version?](#upgrades-0) below.

To ensure a stable configuration, Adobe recommends that you install **the exact same version** on all your Campaign servers. In addition, except mentioned otherwise in the [Release notes](release-notes.md), the client console must be on **the exact same version** as the server instance. Learn how to upgrade your client console [in this page](../start/connect.md#upgrade-ac-console).

## Keep your client console up to date {#ac-upgrades}

As a Campaign Managed Services customer, when a new Campaign version is available, your server infrastructure is upgraded by Adobe without any further action on your part.

Because the server upgrade happens automatically, your **client console** is the one place where a gap can appear if it isn't updated at the same time. If your console version doesn't match your server version:

* You may lose the ability to connect to your Campaign instance until the console is updated.
* Your console stops benefiting from the fixes and security updates shipped in the version your server has already moved to — even though the server itself is current.

To avoid this, upgrade your client console as soon as you're notified of a new version. Learn how to [upgrade your client console](../start/connect.md#upgrade-ac-console).

Note that, as a customer, you must also ensure that you are using the latest supported versions of the systems listed in the [Compatibility matrix](compatibility-matrix.md).

## Frequently Asked Questions {#upgrades-faq}

### How to check my Campaign version? {#version}

To check your Campaign version, access the **Help > About…** menu from the client console.

![](assets/ac-version.png)

You access the following information:

* The **version** number of your client console and application server. In the sample above, the version is 8.1.5 for both the client console and the Application server.
* The SHA number, between parenthesis.
* A link to contact Adobe Customer Care.
* Links to Adobe Privacy Policy, Terms of Use and Cookies Policy.

>[!NOTE]
>
>If the version shown for your client console doesn't match the version shown for your Application server, upgrade your console as described in [Keep your client console up to date](#ac-upgrades).

### How can I be informed of the release of a new version? {#upgrades-0}

New versions and which changes they bring — including security fixes — are listed in the [Release Notes](release-notes.md). Once a new version is available, your Adobe representative contacts you and upgrades your server environments; you'll separately need to upgrade your client console (see [Keep your client console up to date](#ac-upgrades)).

To be informed of new Experience Cloud solution releases and their content, subscribe to the [Adobe Priority Product Updates](https://www.adobe.com/subscription/priority-product-update.html){target="_blank"} communication.

You can also visit [Campaign Community](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"} to be informed about release updates.

### Why does my organization need an upgrade? {#upgrades-1}

Upgrading ensures that your account is secure from vulnerabilities and is using up-to-date performance technology.

Typically, upgrading to the latest version brings:

* **Improved security**

  Security needs constant focus and proactive maintenance. Security risks are omnipresent and cannot be ignored — every upgrade for Campaign improves security. A combination of technologies work together to power Adobe Campaign, and all of them must be kept up to date. Adobe applies these updates to your server automatically; upgrading your client console in step ensures the same protection extends to it.

* **Improved support**

  Most critical issues are resolved with upgrades and can be avoided altogether. Regular upgrades help reduce the challenges you face and increase efficiency. Customer Care volume is reduced, allowing for speedier resolutions and more attention to issues that aren't related to upgrades.

* **Improved maintenance and stability**

  Over time, the Adobe Campaign team identifies ways to improve the stability and performance of the product, as well as fix known issues. Upgrading brings your instance up to date with these improvements and eliminates common challenges seen by organizations experiencing rapid growth and/or complexity within their Campaign instances. Improvements across the technology stack powering Campaign are felt across both marketing and IT teams in your organization.

* **Stay connected**

  Your client console can only communicate reliably with a server running the same version. Keeping your console current — every time your server is upgraded — is what keeps this connection, and the security and fixes that come with it, intact.

### What is the process and timeline for an upgrade? {#upgrades-2}

As a v8 customer, Adobe manages your server upgrade end-to-end:

1. When a new version is available, or your account is identified as needing to move to one, your Adobe representative notifies you.
1. Adobe upgrades your server infrastructure — no action is required from you for this step.
1. On your side, the only action needed is upgrading your client console to match, and confirming the systems in your [Compatibility matrix](compatibility-matrix.md) are still supported. See [Keep your client console up to date](#ac-upgrades).

A team of dedicated Customer Care Representatives, Product Managers, Engineers, TechOps Specialists, and Product Consultants is here to assist and ensure the experience is smooth.

>[!NOTE]
>
>Critical security patches may be applied to your hosted environment outside of this notification cycle — see the note at the top of this page.
