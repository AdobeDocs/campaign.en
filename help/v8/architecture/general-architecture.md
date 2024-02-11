---
title: General architecture
description: Learn more about Adobe Campaign architecture and components. Find out more about personalizing your Client Console and environment. 
feature: Architecture, Deployment
role: Admin, Developer
level: Beginner
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
---
# General architecture{#general-architecture}

The typical Adobe Campaign solution deployment consists of the following components:

* **Personalized Client Environment**

  Intuitive graphical interface in which users can communicate and track marketing offers, create campaigns, review and manage all marketing activities, programs and plans - including emails, workflows and landing pages -, create and manage customer profiles, and create audiences.

* **Development Environment**

  Server-side software that executes the marketing campaigns through chosen communication channels, including emails, SMS, push notifications, direct mail, web or social, based on the rules and workflows defined in the user interface.

* **Database Containers**

  Based on relational database technology, the Adobe Campaign Cloud Database stores all information, campaign components, offers, workflows, and campaign results in database containers.

## Personalized Client Environment {#client-env}

The application can be accessed in different ways: Rich client, Thin client, or API integration.

![](../assets/do-not-localize/glass.png) [Learn more about Campaign presentation layer](../start/ac-components.md).

## Development environment {#dev-env}

Adobe Campaign is a single platform with different applications to create an open and scalable architecture. The Adobe Campaign platform is written on a flexible application layer and is easily configurable to meet your business needs. The distributed architecture ensures linear system scalability scaling from thousands of messages to millions of messages.

Some Campaign modules operate continuously, while others are started up occasionally to perform administrative tasks (e.g. to configure the database connection) or to run a recurrent task (e.g. consolidating tracking information).

There are three types of Adobe Campaign modules:

* **Multi-instance modules**: a single process is run for all instances. This applies to the following modules: web, syslogd, trackinglogd and watchdog.
* **Mono-instance modules**: one process is run per instance. This applies to the following modules: mta, wfserver, inMail, sms and stat.
* **Utility modules**: these are modules that are run occasionally to perform occasional or recurrent operations (cleanup, config, downloading tracking logs, etc.).

The main processes are:

* **Application server** (nlserver web) - This process exposes the full range of Adobe Campaign functionality via Web Services APIs (SOAP / HTTP + XML). Furthermore, it can dynamically generate the Web pages used for HTML-based access (reports, Web forms, etc). To achieve this, this process includes an Apache Tomcat JSP server. This is the process to which the Console connects.

* **Workflow engine** (nlserver wfserver) - This process executes the workflow processes defined in the application. It also handles periodically executed technical workflows, including:

  * **Tracking**: Recovers and consolidates tracking logs, so that you can retrieve the logs from the redirection server and create the aggregate indicators used by the reporting module.
  * **Cleanup**: Cleans the database, and purges old records and avoid the database growing exponentially.
  * **Billing**: Sends an activity report for the platform (size of the database, number of marketing actions, etc.).

* **Delivery Server** (nlserver mta) - Adobe Campaign has native email broadcast functionality. This process functions as an SMTP mail transfer agent (MTA). It performs "one-to-one" personalization of messages and handles their physical delivery. It runs using delivery jobs and handles automatic retries. In addition, when tracking is enabled, it automatically replaces the URLs so that they point to the redirection server. This process can handle the customization and automatic sending to a third-party router for SMS, fax and direct mail.

* **Redirection server** (nlserver webmdl) - For email, Adobe Campaign automatically handles open and click tracking (transactional tracking at the Web site level is a further possibility). To achieve this, the URLs incorporated in the email messages are rewritten in order to point to this module, which registers the passing of the internet user before redirecting them to the required URL.

  To guarantee highest availability, this process is fully independent from the database: the other server processes communicate with it using SOAP calls (HTTP, HTTP(S) and XML) only. Technically, this functionality is implemented in an extension module of an HTTP server (ISAPI extension in IIS, or a DSO Apache module, etc.) and is available in Windows only.
  
Other more technical processes are also available:

* **Managing bounce emails** (nlserver inMail) - This process enables you to automatically pick up email from mailboxes configured to receive bounced messages that are returned in case of delivery failure. These messages then undergo rule-based processing to determine the reasons for non-delivery (unknown recipient, quota exceeded, etc.) and to update the delivery status in the database. All these operations are fully automatic and preconfigured.

* **SMS delivery status** (nlserver sms) - This process polls the SMS router to collect progress status and update the database.

* **Writing log messages** (nlserver syslogd) - This technical process captures log messages and traces generated by the other processes and writes them to the hard disk. This makes ample information available for diagnosis in case of problems.

* **Writing tracking logs** (nlserver trackinglogd) - This process saves to disk the tracking logs generated by the redirecting process.

* **Writing inbound events** (nlserver interactiond) - This process ensures the recording to the disk of inbound events, within the framework of Interaction.

* **Supervising modules** (nlserver watchdog) - This technical process acts as a primary process which spawns the others. It also monitors them and relaunches them automatically in case of incidents, thus maintaining maximum system uptime.

* **Statistics server** (nlserver stat) - This process maintains statistics on the number of connections, the messages sent for each mail server which messages are sent to, as well as their limitations (highest number of simultaneous connections, messages per hour/ and or connection). It also lets you federate several instances or machines if they share the same public IP addresses.


## Database containers {#db-containers}

In its [Enterprise (FFDA) deployment](enterprise-deployment.md), the Adobe Campaign Cloud database relies on [!DNL Snowflake] which contains the functional data (profiles, subscriptions, content, etc.), the technical data (delivery jobs and logs, tracking logs, etc.) and the work data (purchases, leads) for the solution, and all Adobe Campaign components communicate with the database in order to perform their specific tasks.

You can deploy Adobe Campaign using the pre-defined database and schemas, and if needed this pre-defined environment can be extended. All data within the data mart is accessed by Adobe Campaign via SQL calls. Adobe Campaign also provides a full complement of Extract Transform and Load (ETL) tools to perform data import and export of data into and out of the system.

![](assets/data-flow-diagram.png) 


>[!CAUTION]
>
>With **Campaign Managed Cloud Services**, your environment and initial configuration have been set by Adobe, according to the terms of your license agreement. You are not allowed to modify installed built-in packages, built-in schemas or reports.
>
>If you need to use a Campaign add-on or a specific capability which has not been provisioned for you, you must contact **Adobe Customer Care**.

## Database storage {#db-storage}

Total storage allowance is split between the main database and the (optional) Snowflake secondary database. Where data is stored should be determined at implementation or upgrade time, depending on customer-specific use-cases.

Learn how to monitor your database usage in [Campaign Control Panel documentation](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring.html){target="_blank"}.