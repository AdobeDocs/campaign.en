---
title: Get started with Campaign architecture
description: Discover environments and deployment basics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 562b24c3-6bea-447f-b74c-187ab77ae78f
---
# Get Started with Campaign architecture{#gs-ac-archi}

## Environments 

Campaign is made available as individual instances with each instance representing a complete Campaign environment.

Three types of environments available with Campaign Cloud Service:

* **Production environment**: hosts the applications for the business practitioners.

* **Stage environment**: used for various performance and quality tests before changes to the application are pushed to the production environment.

* **Development environment**: allows developers to implement Campaign under the same runtime conditions as the stage and production environments.

You can export and import packages from one environment to another.

![](../assets/do-not-localize/book.png) Learn more about packages in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/working-with-data-packages.html)

## Mid-sourcing deployment{#mid-sourcing-deployment}

General communication between servers and processes is carried out according to the following schema:

![](assets/architecture.png) 

* The execution and bounce management modules are disabled on the instance.

* The application is configured to perform message execution on a remote "mid-sourced" server that is driven using SOAP calls (over HTTP or HTTPS).

>[!NOTE]
>
> Campaign v8 relies on a hybrid architecture. If you are transitioning from Campaign Classic v7, note that all deliveries go through the mid-sourcing server. 
> As a consequence, internal routing is **not possible** in Campaign v8, and the external account has been disabled accordingly.

### Split delivery execution {#split}

According to your Campaign v8 package, you are provisioned with a specific number of mid-sourcing instances in charge of executing deliveries. 

To ensure better performances, the Routing external account containing the configuration of channels is configured by default with the **Split** option activated.

![](assets/splitted-delivery.png) 

This option allows deliveries to be automatically splitted accross your mid-sourcing instances in order to be delivered faster to the recipients. This operation is transparent when executing the delivery from the marketing instance: once the delivery has been sent, all the logs are consolidated together, before being sent back to the marketing instance into a single delivery object.

As a Managed Cloud Services user, Adobe configure all your routing external accounts for your channels with the Split option enabled. It is highly recommended to keep this option activated to ensure better thoughputs.

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

![](../assets/do-not-localize/book.png) Learn more about Transactional messaging events in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html#about-transactional-messaging-datamodel)