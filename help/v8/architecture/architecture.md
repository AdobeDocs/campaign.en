---
title: Get started with Campaign architecture
description: Discover environments and deployment basics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
---
# Get Started with Campaign architecture{#gs-ac-archi}

## Environments {#environments}

Campaign is made available as individual instances with each instance representing a complete Campaign environment.

Two types of environments are available:

* **Production environment**: hosts the applications for the business practitioners.

* **Non-production environment**: used for various performance and quality tests before changes to the application are pushed to the production environment.

You can export and import packages from one environment to another.

![](../assets/do-not-localize/book.png) Learn more about packages in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html){target="_blank"}

## Deployment models{#ac-deployment}

Two deployment models are available:

* **Campaign FDA [!DNL Snowflake] deployment**

    In its [[!DNL Snowflake] FDA deployment](fda-deployment.md), [!DNL Adobe Campaign] v8 is connected to [!DNL Snowflake] to access data through Federated Data Access capability: you can access and process external data and information stored in your [!DNL Snowflake] database without changing the structure of Adobe Campaign data. PostgreSQL is the primary database, and Snowflake is the secondary database. You can extend your data model and store your data on Snowflake. Subsequently, you can run ETL, segmentation and reports on a large data set with outstanding performances.

* **Campaign Enterprise (FFDA) deployment**

    In the context of an [Enterprise (FFDA) deployment](enterprise-deployment.md), [!DNL Adobe Campaign] v8 works with two databases: a local [!DNL Campaign] database for the user interface real-time messaging and unitary queries and write through APIs, and a Cloud [!DNL Snowflake] database for campaign execution, batch queries and workflow execution.

    Campaign v8 Enterprise brings the concept of **Full Federated Data Access** (FFDA): all data is now remote on the Cloud Database. With this new architecture, Campaign v8 Enterprise (FFDA) deployment simplifies data management: no index is required on the Cloud Database. You just need to create the tables, copy the data and you can start. The Cloud database technology does not require specific maintenance to guarantee the level of performance.


## Message Center architecture{#transac-msg-archi}

Transactional messaging (Message Center) is the Campaign module designed for managing trigger messages. 

![](../assets/do-not-localize/glass.png) Learn how to send transactional messages in [this section](../send/transactional.md).

In response to an action of a customer on a website, an event is sent Campaign through a REST API, and the message template is populated with the information or data provided through the API call, and a transactional message is sent in real-time to the customer. These messages can be sent individually or in batches via email, SMS or push notifications. 

In this specific architecture, execution cell is separated from the control instance to ensure high availability and load management.

* The **Control instance** (or Marketing instance) is used by marketers and IT teams to create, configure and publish message templates. This instance also centralize event monitoring and history.
    
    ![](../assets/do-not-localize/glass.png) Learn how to create and publish message templates in [this section](../send/transactional.md).

* The **Execution instance** retreives incoming events (password reset or orders from a website for example) and sends out personalized messages. There can be more than one execution instance to process messages via the load-balancer and scale the number of events to be proceeded for maximum availability.

>[!CAUTION]
>
>The control instance and the execution instance(s) must be installed on different machines. They cannot share the same Campaign instance.

![](assets/messagecenter_diagram.png)

### Authentication

To use these capabilities, Adobe Campaign users log on to the control instance to create transactional message templates, generate the message preview using a seed list, display reports and monitor execution instance(s).

* Single execution instance
    When interacting with an Adobe hosted Message Center execution instance, an external system can first retrieve a session token (that by default expires in 24 hours), by making an api call to the session logon method, using a provided account login and password.
    Then, with the sessionToken provided by the execution instance in response to the above call, the external application can make SOAP api invocations (rtEvents or batchEvents) to send communications, without the need to include in each SOAP call the account login and password.
 
* Multiple execution instances
    In a multi-cell execution architecture with multiple execution instances behind a load balancer, the logon method invoked by the external application is going through the load balancer: for that reason, a token-based authentication cannot  be used. A user/password-based authentication is required. 

![](../assets/do-not-localize/book.png) Learn more about Transactional messaging events in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel){target="_blank"}
