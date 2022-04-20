---
title: What's new in Campaign v8
description: Discover key capabilities in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
---
# What's new in Adobe Campaign v8? {#ac-gs-what-is-new}

Adobe Campaign v8 is designed for cross-channel marketers who need the best-in-class cloud solution for cross-channel campaign management with enterprise scale. It provides robust ETL and data management capabilities to help craft and curate the perfect campaign. Its orchestration engine provides for rich multi-touch marketing programs with a core focus on batch-based driven journeys. It also comes paired with a scalable real-time messaging server that enables marketing teams to send pre-defined messages based on a all-inclusive payload from any IT system for things such as password reset, order confirmation, e-receipt’s and much more.

Adobe Campaign v8 brings significant infrastructure, security, deliverability, and monitoring enhancements. 

![](assets/home-page.png) 

## Key capabilities{#key-capabilities}

Key capabilities include:

* **Central workflow management**. Improve the speed and scale of every aspect of your marketing campaigns, from creating segments and preparing messages to delivery. 

    Adobe Campaign makes it easy for you to get your channels in sync, with a single, easy-to-use interface for campaign orchestration. So, your online channels — like email, web, mobile, and social — match your offline channels, including direct mail, call center, in-store, and so on. It empowers you to give your customers a consistent and contextual experience in both digital and traditional channels. Adobe Campaign makes it simple to deliver content to all the paths your customers may take — on any channel.

* **Personalized email marketing**. Create personalized and contextually relevant emails that are consistent with the rest of the customer experience.

    With Adobe Campaign, you can make your emails better, more personalized, and more profitable. Emails are simple to create and easy to deliver. Campaign v8 gives you the flexibility to design, personalize, test, refine, and improve every message you send.

* **Customer data management**. See the whole picture of your customers so you can quickly create personalized campaigns at enterprise scale.

    Adobe Campaign helps you build customer profiles from data gathered across all of your channels. With this profile, you can orchestrate campaigns across channels. By connecting all of your marketing channels, you are able to customize the different journey each customer will take in the way that will make sense to them.

* **Best-in class campaign management**. Adobe Campaign v8 provides marketers with best-in-class capabilities to plan, launch and measure campaigns across channels. 

    Capabilities include an integrated profile that provides a single view of the customer. Data management and segmentation for campaign audience building at scale. Cross-channel workflow management for automating multi-channel and multi-wave campaigns. Integrated email, reducing reliance on costly ESPs. Reporting and analytics for understanding customer behavior and campaign performance.
    
* **Connections to Adobe Experience Platform**. Adobe Campaign v8 supports data connectors with Real-Time CDP and Adobe Experience Platform, so organizations can leverage the real-time unified Customer Profile.
     
    In addition, Adobe Campaign v8 is natively integrated with the real-time journey orchestration capabilities so that marketers can reuse the same templates and delivery capabilities in Adobe Campaign to engage with customers in real-time. These investments will optimize the Adobe Campaign customer experience and unlock new use cases such as the ability to add individualized real-time customer journeys to campaigns.

* **Managed Cloud Services**. Adobe Campaign v8 is available as a Managed Cloud Service, providing proactive oversight, timely alerting, and service governance.

    Adobe Managed Cloud Service provides marketers with a more agile, secure and scalable cross-channel campaign management solution with a low total cost of ownership. The new offering combines services with proactive oversight and timely alerting.

* **Speed and scale**. Adobe Campaign can now leverage cloud scale database technologies to dramatically improve its scale and speed.

    With its [Enterprise (FFDA) deployment](../dev/entreprise-deployment.md), Adobe Campaign v8 leverages the Cloud Database Manager, leading to queries performing up to 200x faster, multi-petabyte scale, increased number of messages per hour, with up to 20M/hour or 1M/hour for transactional messages, and manage up to 200M active profiles with the potential to reach 1B.



>[!CAUTION]
>
>For now, Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 
>
>Migration from an existing Campaign Classic v7 environment is not yet available.
>
>If you are unsure of your deployment model or have any question, please get in touch with your account team.


## Self-service admin interface{#self-service-admin}

As a product administrator, you can manage settings and track usages of each of your Campaign v8 instances with **Campaign Control Panel**. 

Through an intuitive user interface, administrators can monitor usage of key assets, perform advanced tasks such as IP addresses allow listing, SFTP storage monitoring, key management, and more. This self-service interface brings you more flexibility and helps you:

* Quickly make changes to settings by yourself without reaching out to Adobe Support
* Configure settings based on your different business needs at different times
* Enhance security by controlling access settings on a need-by-need basis

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Learn more about Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html){target="_blank"}


## Integrated ecosystem{#integrated}

You can integrate Campaign with a set of powerful Adobe solutions, such as: Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP, and more.

You can also configure predictive send time optimization and predictive engagement scoring with Journey AI, and increase open rates, clicks and revenues.

![](../assets/do-not-localize/glass.png) [Learn more about Campaign integrations](../connect/integration.md)


## Simplification and performances{#ffda}

[Campaign v8 Enterprise](../dev/entreprise-deployment.md) brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. 

With this new offering, Campaign v8 simplifies data management: no index is required on the Cloud Database. You just need to create the tables, copy the data and you can start. [!DNL Snowflake] is the Campaign Cloud Database, it will bring you speed and endurance: no overload of the system activity peaks. The Cloud database technology does not require specific maintenance to guarantee the level of performance. [Learn more](../dev/entreprise-deployment.md)
