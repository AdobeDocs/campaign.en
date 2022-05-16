---
title: What's new in Campaign v8
description: Discover key capabilities in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
---
# What's new in Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 brings significant infrastructure, security, deliverability, and monitoring enhancements. By leveraging [[!DNL Snowflake]](https://www.snowflake.com/), a cloud database technology, Adobe Campaign dramatically improves its scale and speed, with the ability to manage a more significant number of customer profiles, as well as much higher delivery rates and transactions per hour. 

## Key capabilities{#key-capabilities}

Key capabilities include:

* **Speed and scale**. Adobe Campaign v8 leverages the Cloud Database Manager, leading to queries performing up to 200x faster, multi-petabyte scale, increased number of messages per hour, with up to 20M/hour or 1M/hour for transactional messages, and manage up to 200M active profiles with the potential to reach 1B.

* **Connections to the Adobe Experience Platform**. Adobe Campaign v8 supports data connectors with Adobe Experience Platform/RT-CDP, unified Customer Profile, and native integration with Journey Orchestration. These investments will optimize the Adobe Campaign customer experience and unlock new use cases such as the ability to add individualized real-time customer journeys to campaigns.

* **Managed Cloud Services**. Adobe Campaign v8 is available as a best-in-class Managed Cloud Services, providing proactive oversight, timely alerting, and service governance. The value for the marketer is a more agile and scalable cross-channel campaign management.

>[!CAUTION]
>
>For now, Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 
>
>Migration from an existing Campaign Classic v7 environment is not yet available.
>
>If you are unsure of your deployment model or have any question, please get in touch with your account team.

![](assets/home-page.png) 

## Scale{#scale}

Campaign v8 brings end-to-end scale at any step of the process, from targeting to the final reporting:

* Scale the volume of data you can handle (until 8 TB)
* Scale the performance of queries for segmentation and targeting but also data ingestion and egress
* Scale the delivery preparation (from hours to minutes)

## Self-service admin interface{#self-service-admin}

As a product administrator, you can manage settings and track usages of each of your Campaign v8 instances with **Campaign Control Panel**. 

Through an intuitive user interface, administrators can monitor usage of key assets, perform advanced tasks such as IP addresses allow listing, SFTP storage monitoring, key management, and more. This self-service interface brings you more flexibility and helps you:

* Quickly make changes to settings by yourself without reaching out to Adobe Support
* Configure settings based on your different business needs at different times
* Enhance security by controlling access settings on a need-by-need basis

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Learn more about Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html){target="_blank"}



## Simplification and performance increase{#simplification-and-perf-increase}

Campaign v8 brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database.

With this new architecture, Campaign v8 simplifies data management: no index is required on the Cloud Database. You just need to create the tables, copy the data and you can start.

[!DNL Snowflake] is the Campaign Cloud Database, it will bring you speed and endurance: no overload of the system activity peaks. 

The Cloud database technology does not require specific maintenance to guarantee the level of performance.

## Integrated ecosystem

You can integrate Campaign with a set of powerful Adobe solutions, such as: Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP, and more.

You can also configure predictive send time optimization and predictive engagement scoring with Journey AI, and increase open rates, clicks and revenues.

![](../assets/do-not-localize/glass.png) [Learn more about Campaign integrations](../connect/integration.md)

