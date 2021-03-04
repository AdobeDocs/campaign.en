---
solution: Campaign Classic
product: campaign
title: Monitoring guidelines
description: Discover guidelines and best practices to monitor Campaign instance and processes.
audience: production
content-type: reference
topic-tags: introduction
---

# Monitoring guidelines {#monitoring-guidelines}

## Instance monitoring dashboard {#instance-monitoring-dashboard}

The **[!UICONTROL Monitoring]** tab, which is accessible from Campaign Classic homepage, is the main entry point to help you monitor your instance.

It provides a dashboard of what is occuring on your instance: its status (build version, installed packages, etc.), system indicators, logs,  workflows that are currently running, state of last sent deliveries, etc.

Detailed information is available .

![](assets/monitoring_tab.png)

## Monitoring Campaign Classic processes {#monitoring-campaign-classic-processes}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-instance">Monitor your instance</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitor workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitor deliveries</a></p></td>
<td><img src="assets/do-not-localize/icon_database.svg" width="60px"><p><a href="#monitoring-database">Monitor the database</a></p></td></tr>
</table>

Additional ways of monitoring the different Campaign processes are available. They provide several ways of monitoring your instances to make sure that your system is healthy and eventually troubleshoot issues that may occur when setting up workflows, sending deliveries, etc.

### Monitoring your instance {#monitoring-instance}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Automatic monitoring tools**

Several automatic methods are available. to help you monitor your instance. You can, for example, set up email reports with detected anomalies, retrieve a list of indicators in XML format, etc.  for more information.

**Audit trail**

The Audit trail allows you to visualize the complete history of changes related to options, workflows and schemas within your instance.  for more information.

**Control Panel**

The Control Panel allows you to manage several settings of your instance: manage URL permissions, check your instance details like your servers' build versions, etc. It also allows you to monitor the available space on the SFTP servers that are connected to your instance. [Click here](https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html) for more information.

>[!NOTE]
>
>Please note that the Control Panel is accessible to Admin users only, and available for all customers using Adobe Managed Services.

### Monitoring workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Workflow HeatMap**

The Workflow HeatMap provided a visual representation of all the workflows that are running on your instance. It allows you to easily monitor the load on the instance and plan workflows accordingly.  for more information.

**Audit trail**

The Audit trail allows you to visualize all the modifications that have been made in workflows, as well as their current states. .

**Workflows troubleshooting**

Specific actions can be performed when encountering issues with a workflow execution.  for more information

**Workflow status monitoring**

Additionally to the heatmap, you can create a workflow that will let you monitor the status of a set of workflows and send recurring messages to supervisors.  for more information.

**General guidelines**

Following guidelines and best practices when using workflows can help improve performances. For more information, refer to these sections:
* 
* 

### Monitoring deliveries {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**SMTP reports**

SMTP reports display delivery statistics and SMTP errors by domain. 

**Best practices**

 can help you improve their performances.

**Delivery troubleshooting**
Specific actions can be performed when encountering issues with deliveries:
* 
* 
* 
* *on premise hosting models only*

### Monitoring the database {#monitoring-database}

<img src="assets/do-not-localize/icon_database.svg" width="60px">

**Database cleanup workflow**

The Database cleanup workflow allows you to delete obsolete data from your database. It is recommended to avoid exponential growth of the database.  for more information.

**Database performance troubleshooting**

Specific actions can be performed when encountering issues with database performances.  for more information.

**Database maintenance**

*on-premise and hybrid hosting models only*

We recommend that you perform database maintenance on a regular basis to avoid overconsumption of disk space, thus affecting database access.  for more information.

**Backup & restoration**

*on-premise and hybrid hosting models only*

Backing up is essential in order to avoid losing data in the event of a problem (whether physical or system-related) on a machine. .

## Campaign Classic technical principles {#campaign-classic-technical-principles}

Technical resources are available in Campaign Classic documentation. We recommend you get familiar with these topics before performing any technical operation on your instance.

**Hosting models and capabilities**

* 
* 

**Server configuration**

*On-premise & hybrid hosting models only*

* 
* 
* 
* 

**General principles**

* 
* 
* 
* 
* 
* 
