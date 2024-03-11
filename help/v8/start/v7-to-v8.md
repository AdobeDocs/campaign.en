---
title: Transition from Campaign Classic v7 to Campaign v8
description: Learn about the differences between Campaign Classic v7 and Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
---
# Transition from [!DNL Campaign Classic] v7 to [!DNL Campaign] v8{#gs-matrix}

As a former [!DNL Campaign Classic] v7 user, you should not expect any big disruption in the way you usually interact with [!DNL Adobe Campaign]. Most changes in v8 are not visible, except for small changes surfacing in the UI and configuration steps. 

>[!AVAILABILITY]
>
>* For now, Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. [Learn more](#cloud-services)
>
>* Automated migration from an existing Campaign Classic v7 environment is not yet available.


## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 is available as a **Managed Cloud Service**. 

Adobe Campaign Managed Cloud Services provides a Managed Cloud Services platform for designing cross-channel customer experiences and provides an environment for visual campaign orchestration, real time interaction management and cross channel execution. Learn more about Campaign Managed Cloud Services in the [product description page](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

The new offering combines best-in-class services with proactive oversight and timely alerting, focusing on three areas:

* **Cloud agility** — automation by Adobe, featuring optimized, standardized cloud deployments for more predictable performance, greater agility, and improved self-service productivity.
* **Service experience** — proactive availability, capacity, and performance monitoring and response to prevent disruptions, resolve incidents faster, and review service regularly for continuous improvement.
* **Deep Campaign expertise** — high-affinity service from expert Customer Engineering teams to meet functional, technical, or deliverability needs, cut deployment risk, and improve change management.

As a former [!DNL Campaign Classic] user, note that most of the [!DNL Campaign Classic] v7 features are available with [!DNL Campaign] v8, except a small set of them, listed in [this section](#gs-removed).

>The new cloud architecture enables Campaign to streamline processes, reduce costs, manage risks, and improve data security. Your Campaign v8 environment comes with a dedicated Virtual Private Cloud (VPC) that is pre-configured for you.


## Hybrid architecture {#hybrid-archi}

Campaign v8 relies on a **hybrid architecture**. If you are transitioning from Campaign Classic v7, note that all deliveries go through the mid-sourcing server. 

As a consequence:

* Internal routing is **not possible** in Campaign v8, and the external account has been disabled accordingly,
* Status of the deliveries is not instantly updated - A technical process runs on the Marketing instance which will update the delivery statuses in a timely manner.


![](../assets/do-not-localize/glass.png) Learn more about sending transactional message proofs when transitioning from v7 on [this page](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] and [!DNL Snowflake] {#ac-gs-snowflake}

In its [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 works with two databases: a local [!DNL Campaign] database for the user interface real-time messaging and unitary queries and write through APIs, and a cloud [!DNL Snowflake] database for campaign execution, batch queries and workflow execution.

Campaign v8 Enterprise brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. With this new architecture, Campaign v8 Enterprise (FFDA) deployment simplifies data management: no index is required on the Cloud Database. You only need to create the tables, copy the data and you can start. The Cloud database technology does not require specific maintenance to guarantee the level of performance.

![](../assets/do-not-localize/glass.png) Learn more about [!DNL Campaign] v8 architecture in [this page](../architecture/architecture.md).


## Use your Adobe ID to connect to Campaign{#adobe-id}

Campaign users connect through their Adobe ID only. The same Adobe ID is used to keep all your Adobe plans and products associated with a single account, for all Adobe Experience Cloud solutions. 

![](../assets/do-not-localize/glass.png) Learn how to connect to [!DNL Campaign] in [this page](connect.md).

## Analyze data with cubes{#adobe-reporting}

Use the Marketing Analytics module to analyze and measure data, calculate statistics, simplify and optimize report creation and calculation. In addition, create reports and build target populations: once identified, they are stored in lists that can be used in Adobe Campaign (targeting, segmentation, etc.).

With Adobe Campaign v8, cube reports are optimized and bring better scale capabilities than Campaign Classic v7. In that specific deployment model, former limitations on cubes do not apply in Campaign v8. Learn more about cubes in [this section](../../v8/reporting/gs-cubes.md).

## Unavailable features{#gs-unavailable-features}

Please note that some capabilities are not available in the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md) of Campaign, such as:

* Marketing Resource Management
* Coupons
* Web tracking
* Surveys

## Unsupported features{#gs-removed}

Some historic Campaign Classic v7 capabilities are no longer supported with Campaign v8, such as:

* Social Marketing with Facebook
* ACS Connector (Prime offering)
* Integration with LDAP
* User/Password sign in
* Hybrid/On-premise deployment models


>[!NOTE]
>
>Some non-available or unsupported features may still be visible in the user interface.
