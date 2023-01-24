---
title: Connect to Campaign v8
description: Learn how to connect to Adobe Campaign v8 and install the console on your machine for easier access. 
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
---
# Connect to Adobe Campaign v8{#gs-ac-connect}

Campaign Client Console is a rich client which enables you to connect to your Campaign application server(s). Learn more about Campaign Client Console [in this page](ac-components.md#presentation-layer).

Before starting, you need to:

* Check your system and tools compatibility with Adobe Campaign in the [Compatibility matrix](compatibility-matrix.md)
* Get your Campaign server URL 
* Create your Adobe ID or get your user credentials from your company
* Install Microsft Edge Webview2 runtime on your system (from Campaign Classic 8.4 build version). [Learn more](#webview)

## Microsoft Edge Webview2 runtime installation {#webview}

From Campaign Classic 8.4 build version, installation of Microsoft Edge Webview 2 runtime is required for any console installation.

Web View is installed by default as part of Windows 11 operating system. If it is not already present on your system, Campaign Console Installer will prompt you to download it from [Microsoft Developer website](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}. Note that the download link does not work on the Internet Explorer 11 browser as Microsoft has deprecated its support. Make sure you use a different browser to access the link.

## Download and install the Client Console{#download-ac-console}

When using Campaign for the first time, or if you need to upgrade to a newer version, you need to download the Client Console and install it. 

Two options are available:

1. As a Campaign administrator, connect to Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"} and download the Client Console installation program. You can then install it on your local machine.

1. As a end-user, Adobe can deploy the Console for you: once the Console is updated, you will be prompted to download the latest Client Console version in a pop-up window. 

>[!CAUTION]
>
>Adobe recommends leaving the option **[!UICONTROL No longer ask this question]** unselected to make sure that all users are alerted when a new version of the Console is available.  If this option is selected the user will not be informed of new available versions.

## Create your connection{#create-your-connection}

Once the Client Console is newly installed, follow the steps below to create the connection to the application server:

1. Start the Console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

1. Click the link in the top right-hand corner of the credentials fields to access the connection configuration window.

1. Click **[!UICONTROL Add > Connection]** and enter the label and URL of the Adobe Campaign application server.

1. Specify a connection to your Adobe Campaign application server via a URL. Use either a DNS or an alias of the machine, or your IP address.

   For example, you can use the [`https://<machine>.<domain>.com`](https://myserver.adobe.com) type URL.

1. Check the option **[!UICONTROL Connect with an Adobe ID]**.

1. Click **[!UICONTROL Ok]** to save your settings.

You can add as many connections as needed to connect to your test, stage and production environments for example.

>[!NOTE]
>
>The **[!UICONTROL Add]** button lets you create **[!UICONTROL folders]** to organize all your connections. Simply drag and drop each connection into a folder.

## Log on to Adobe Campaign {#logon-to-ac}

To log on to an existing instance, follow the steps below:

1. Start the Console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

1. Click the link in the top right-hand corner of the credentials fields to access the connection configuration window.
   
   ![](assets/connectToCampaign.png) 

1. Select the Campaign instance you need to log in to.

1. Click **[!UICONTROL Ok]**.

1. You can then sign in to Campaign with [your Adobe ID](#connect-ims).

   ![](assets/adobeID.png) 

>[!NOTE]
>
>For campaign classic 8.4 build versions, Adobe Campaign client console may ask for proxy credentials two times during proxy authentication. This is due to the fact that Microsoft Edge Webview2 does not save proxy credentials in the cache/password store unlike Internet Explorer.

## Grant access to users{#grant-access}

Adobe Campaign lets you define and manage the rights assigned to the various operators.

As a Campaign administrator, you are responsible for creating the operators and sharing their credentials with the users. 

Learn more about users and how to define their permissions in [this section](gs-permissions.md).


## Connect to Campaign with your Adobe ID{#connect-ims}

Campaign users connect to the Adobe Campaign console using their Adobe ID, through Adobe Identity Management System (IMS). They can use same ID all Adobe solutions. The connection is saved when using Adobe Campaign with other solutions.

Learn more about Adobe IMS in [this page](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

## Web access{#web-access}

Certain parts of the application can be accessed via a web browser using an HTML user interface: reporting, delivery approval, instance monitoring, and more. 

The Web access provides an interface that is similar to the console but with a reduced set of functionalities.

For example, for a given operator, a campaign will show up with the following options in the console:

![](assets/campaign-from-console.png)

Whereas with Web access, the options will mainly enable viewing:

![](assets/campaign-from-web.png)

Web access is also used to in the validation process: operators can click on the approval request email and connect to Campaign through their web browser to validate or reject a delivery content or budget.

To access to your Campaign instance from the web, the URL is:  `https://<your adobe campaign server>:<port number>/view/home`.
