---
title: What's new in Campaign v8
description: Discover key capabilities in Adobe Campaign v8
feature: Overview
role: User
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
---
# Adobe Campaign v8 key capabilities {#ac-gs-what-is-new}

Adobe Campaign v8 is designed for cross-channel marketers who need the best-in-class cloud solution for cross-channel campaign management with enterprise scale. It provides robust ETL and data management capabilities to help craft and curate the perfect campaign. Its orchestration engine provides for rich multi-touch marketing programs with a core focus on batch-based driven journeys. It also comes paired with a scalable real-time messaging server that enables marketing teams to send pre-defined messages based on a all-inclusive payload from any IT system for things such as password reset, order confirmation, e-receipt's and much more.

Adobe Campaign v8 brings significant infrastructure, security, deliverability, and monitoring enhancements. It is available as a **Managed Cloud Service** which combines services with proactive oversight and timely alterting. Learn more about Campaign Managed Cloud Services [in this section](#acms-desc).

![](assets/home-page.png) 

## Key capabilities{#key-capabilities}

### Campaign Web user interface{#new-web-ui}

Adobe Campaign v8 offers a **new web user interface** alongside the traditional client console. This modern, intuitive interface is designed for marketers who need faster campaign creation and improved accessibility.

**Key benefits:**

* **Modern design** - Clean, responsive interface accessible from any browser
* **Simplified workflows** - Streamlined campaign creation and management
* **Drag-and-drop capabilities** - Visual content design without technical knowledge
* **Faster onboarding** - Minimal learning curve for new users
* **Unified experience** - Shares similarities with Campaign Standard for easy transition

Starting Campaign v8.6, the Campaign Web UI is available through Adobe Experience Cloud, enabling seamless access to all Adobe solutions.

[Learn more about the Campaign Web user interface](https://experienceleague.adobe.com/en/docs/campaign-web/v8/campaign-web-home){target="_blank"}

### Central workflow management{#central-wf-mgt}

Improve the speed and scale of every aspect of your marketing campaigns, from creating segments and preparing messages to delivery. 

Adobe Campaign makes it easy for you to get your channels in sync, with a single, easy-to-use interface for campaign orchestration. So, your online channels — like email, web, mobile, and social — match your offline channels, including direct mail, call center, in-store, and so on. It empowers you to give your customers a consistent and contextual experience in both digital and traditional channels. Adobe Campaign makes it simple to deliver content to all the paths your customers may take — on any channel.

[Learn more about Campaign workflows](../config/workflows.md)

### Personalized email marketing {#perso-email-mkt}

Create personalized and contextually relevant emails that are consistent with the rest of the customer experience.

With Adobe Campaign, you can make your emails better, more personalized, and more profitable. Emails are simple to create and easy to deliver. Campaign v8 gives you the flexibility to design, personalize, test, refine, and improve every message you send.

[Learn more about personalization capabilities](create-message.md)

### Customer data management {#customer-data-mgt}

See the whole picture of your customers so you can quickly create personalized campaigns at enterprise scale.

Adobe Campaign helps you build customer profiles from data gathered across all of your channels. With this profile, you can orchestrate campaigns across channels. By connecting all of your marketing channels, you are able to customize the different journey each customer will take in the way that will make sense to them.

[Learn more about customer data management](audiences.md)

### Best-in class campaign management {#best-in-campaign-mgt}

Adobe Campaign v8 provides marketers with best-in-class capabilities to plan, launch and measure campaigns across channels. 

Capabilities include an integrated profile that provides a single view of the customer. Data management and segmentation for campaign audience building at scale. Cross-channel workflow management for automating multi-channel and multi-wave campaigns. Integrated email, reducing reliance on costly ESPs. Reporting and analytics for understanding customer behavior and campaign performance.

[Learn more about campaign management](campaigns.md)

    
### Connections to Adobe Experience Platform {#connection-to-aep}

Adobe Campaign v8 supports data connectors with Real-Time CDP and Adobe Experience Platform, so organizations can leverage the real-time unified Customer Profile.
     
In addition, Adobe Campaign v8 is natively integrated with the real-time journey orchestration capabilities so that marketers can reuse the same templates and delivery capabilities in Adobe Campaign to engage with customers in real-time. These investments will optimize the Adobe Campaign customer experience and unlock new use cases such as the ability to add individualized real-time customer journeys to campaigns.
    
You can also configure predictive send time optimization and predictive engagement scoring with Journey AI, and increase open rates, clicks and revenues.

[Learn more about Campaign integrations](../connect/integration.md)


### Managed Cloud Services {#acms-desc}

Adobe Campaign v8 is available as a Managed Cloud Service, providing proactive oversight, timely alerting, and service governance. Adobe Managed Cloud Service provides marketers with a more agile, secure and scalable cross-channel campaign management solution with a low total cost of ownership. The new offering combines services with proactive oversight and timely alerting.

The managed services approach enables marketers to take advantage of the operational scale and economics of cloud infrastructure without the need for heavy support from internal IT resources. Adobe consulting and implementation teams work with you to assess your marketing plans, existing practices, data requirements, and messaging volume, and then they recommend the most appropriate service, support, and deliverability packages. The Adobe Campaign Managed Cloud Services team can then monitor and report on campaign performance, brand reputation, customer experience metrics, and more.

[!BADGE PDF]{type=Informative} [Read out this whitepaper](assets/do-not-localize/IDC-Report-BusinessValueOfAdobeCampaign.pdf){target="_blank"} to learn more about the business value of Adobe Campaign Managed Cloud Services.

Note that the new cloud architecture enables Campaign to streamline processes, reduce costs, manage risks, and improve data security. Your Campaign v8 environment comes with a dedicated Virtual Private Cloud (VPC) that is pre-configured for you.


>[!AVAILABILITY]
>
>* Campaign v8 is **only** available as a Managed Cloud Service, and cannot be deployed on an on-premise or hybrid environments. 
>
>* Automated migration from an existing Campaign Classic v7 environment is not yet available.


### Speed and scale {#speed-scale}

Adobe Campaign can now leverage cloud scale database technologies to dramatically improve its scale and speed.

[Campaign v8 Enterprise](../architecture/enterprise-deployment.md) brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. With this new offering, Campaign v8 simplifies data management: no index is required on the Cloud Database. You just need to create the tables, copy the data and you can start. [!DNL Snowflake] is the Campaign Cloud Database, it brings you speed and endurance: no overload of the system activity peaks. The Cloud database technology does not require specific maintenance to guarantee the level of performance. 

[Learn more about Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md)

### Performance at scale {#performance-metrics}

Campaign v8 Enterprise delivers exceptional performance for high-volume marketing operations:

* **Batch processing** - Up to **20 million operations per hour** for large-scale campaign execution
* **Transactional messaging** - **1 million messages per hour** for real-time communications
* **Rapid audience building** - Query and segment millions of profiles in minutes instead of hours
* **Cloud database** - Snowflake technology eliminates system overload during peak activity

This performance enables organizations to execute complex, multi-touch campaigns at enterprise scale without compromising speed or reliability.

### New and enhanced features {#new-features}

Campaign v8 introduces powerful new capabilities and enhancements:

**AI Assistant**

Leverage generative AI to accelerate content creation:

* Generate email, SMS, and push notification content automatically
* Adapt messaging to your brand voice and guidelines
* Brand alignment scoring to ensure consistency
* Reduce content creation time while maintaining quality

**Rich push notifications**

Create engaging mobile experiences with:

* Images, videos, and carousels in push notifications
* Interactive buttons and timers
* Enhanced customization for iOS and Android
* Improved engagement through visual storytelling

**Upgraded SMS infrastructure (v2.0)**

* Enhanced reliability and delivery rates
* Better compatibility with SMPP connectors
* Improved throughput for high-volume SMS campaigns
* Advanced delivery monitoring and reporting

**Enhanced integrations**

* **Adobe Experience Manager as a Cloud Service** - Seamless content management and asset integration
* **REST APIs** - Modern API architecture for easier integrations and development
* **Dynamic Reporting** - Advanced analytics capabilities for Campaign Standard users transitioning to v8

### Automatic upgrades and maintenance {#automatic-upgrades}

Campaign v8 Managed Cloud Services eliminates the burden of manual upgrades:

* **Continuous delivery model** - Automatic upgrades to the latest stable version
* **Zero downtime** - Upgrades performed with minimal impact on operations
* **Immediate access** - Get new features and security patches as soon as they're released
* **Reduced IT burden** - Adobe manages all infrastructure maintenance and updates
* **Coordinated scheduling** - Adobe works with you to plan upgrade timing

This approach ensures your Campaign instance is always secure, optimized, and equipped with the latest capabilities without requiring internal IT resources for upgrade planning and execution.

## Self-service admin interface{#self-service-admin}

As a product administrator, you can manage settings and track usages of each of your Campaign v8 instances with **Campaign Control Panel**. 

Through an intuitive user interface, administrators can monitor usage of key assets, perform advanced tasks such as IP addresses allow listing, SFTP storage monitoring, key management, and more. This self-service interface brings you more flexibility and helps you:

* Quickly make changes to settings by yourself without reaching out to Adobe Support
* Configure settings based on your different business needs at different times
* Enhance security by controlling access settings on a need-by-need basis

![](assets/subdomain1.png)

[Learn more about Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html){target="_blank"}


