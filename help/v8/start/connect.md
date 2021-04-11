---
solution: Campaign Classic
product: campaign
title: Learn how to connect to Campaign v8
description: Connect to Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917,ed68cb7f-da6a-470c-bcd2-e07660f48b17
---
# Connect to Adobe Campaign v8{#gs-ac-connect}

Campaign Client Console is a rich client which enables you to connect to your Campaign application server(s).

>[!CAUTION]
>
>Before starting, you need to check Campaign [Compatibility matrix](compatibility-matrix.md), get your Campaign server URL and user credentials.

## Download and install the Client Console

When using Campaign for the first time, or if you need to upgrade to a newer version, you need to download the Client Console and install it. 

Two options are available:

1. As a Campaign administrator, connect to Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) and download the Client Console installation program. You can then install it on your local machine.

1. As a end-user, Adobe can deploy the Console for you: once the console is updated, you will be prompted to download the latest client console version in a pop-up window. 

>[!CAUTION]
>
>Adobe recommends leaving the option **[!UICONTROL No longer ask this question]** unselected to make sure that all users are alerted when a new version of the console is available.  If this option is selected the user will not be informed of new available versions.

### Tutorial video

This video shows how to install and setup the Adobe Campaign Client.

>[!VIDEO](https://video.tv.adobe.com/v/35124?quality=12)

## Create your connection

Once the client console is installed, follow the steps below to create the connection to the application server:

1. Start the console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

1. Click the link in the top right-hand corner of the credentials fields to access the connection configuration window.

1. Click **[!UICONTROL Add > Connection]** and enter the label and URL of the Adobe Campaign application server.

1. Specify a connection to your Adobe Campaign application server via a URL. Use either a DNS or an alias of the machine, or your IP address.

   For example, you can use the [`https://<machine>.<domain>.com`](https://myserver.adobe.com) type URL.

1. If Adobe Identity Management System (IMS) is configured for your organization, check the option **[!UICONTROL Connect with an Adobe ID]** .

1. Click **[!UICONTROL Ok]** to save your settings.

You can add as many connections as needed to connect to your test, stage and production environments for example.

>[!NOTE]
>
>The **[!UICONTROL Add]** button lets you create **[!UICONTROL folders]** to organize all your connections. Simply drag and drop each connection into a folder.

## Log on to Adobe Campaign 

To log on to an existing instance, follow the steps below:

1. Start the console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

1. Click the link in the top right-hand corner of the credentials fields to access the connection configuration window.

1. Select the Campaign instance you need to log in to.

1. Click **[!UICONTROL Ok]**

1. Enter your user login credentials and click **[!UICONTROL LOG IN]**

## Grant access to users

Adobe Campaign lets you define and manage the rights assigned to the various operators. These are a set of rights and restrictions that authorize or deny:

* Access to certain functionalities (via the named rights),
* Access to certain records,
* Creation, modification and/or deletion of records (actions, contacts, campaigns, groups, etc.).

The permissions apply to operator profiles or operator groups.

Learn more about users and how to define their permissions in [this section](permissions.md).

## Web access

Certain parts of the application can be accessed via a simple web browser using an HTML user interface: reporting, delivery approval, instance monitoring, and more.
