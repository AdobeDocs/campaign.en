---
title: Connect to Campaign with the client console
description: Learn how to install Campaign client console on your machine and connect to Adobe Campaign
feature: Client Console
role: User
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
---
# Connect to Campaign with the client console{#gs-ac-connect}

To connect to Campaign with the client console, you must first install and configure it.

Before starting, you need to:

* Check your system and tools compatibility with Adobe Campaign in the [Compatibility matrix](compatibility-matrix.md)
* Get your Campaign server URL 
* Create your Adobe ID, or get your user credentials from your company
* Install Microsft Edge Webview2 runtime on your system. [Learn more](#webview)


>[!NOTE]
>
>You can also connect to Campaign Web user interface using a web browser. Learn more about the new Campaign Web User Interface in [this documentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.


## Install the client console{#download-ac-console}

### Microsoft Edge Webview2 runtime {#webview}

From Campaign Classic 8.4 build version, installation of Microsoft Edge Webview 2 runtime is required for any client console installation.

Web View is installed by default as part of Windows 11 operating system. If it is not already present on your system, Campaign client console installation program will prompt you to download it from [Microsoft Developer website](http://www.adobe.com/go/acc-ms-webview2-runtime-download){target="_blank"}. Note that the download link does not work on the Internet Explorer 11 browser as Microsoft has deprecated its support. Make sure you use a different browser to access the link.

### Download the Console{#install-ac-console}

When using Campaign for the first time you need to download the client console and install it. 

Two options are available to download the client console:

1. As a Campaign administrator, connect to Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html){target="_blank"}.

1. As a end-user, your Campaign administrator deploys the client console for you, and makes it available through a dedicated URL.

Once the client console installation program is downloaded, install it on your local machine.

Note that you cannot change the client console language once it is installed.

## Create your connection{#create-your-connection}

Once the client console is installed, follow the steps below to create the connection to the application server:

1. Start the Console and browse the link in the right-hand corner to access the connection configuration screen.

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

Campaign users connect to the Adobe Campaign console using their Adobe ID, through Adobe Identity Management System (IMS). They can use same ID all Adobe solutions. The connection is saved when using Adobe Campaign with other solutions. Learn more about Adobe IMS in [this page](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.

To log on to an instance, follow the steps below:

1. Start the Console and browse the link in the right-hand corner to access the connection configuration screen.

   ![](assets/connectToCampaign.png) 

1. Select the Campaign instance you need to log in to.

1. Click **[!UICONTROL Ok]**.

You can then sign in to Campaign with your Adobe ID.

![](assets/adobeID.png) 

>[!NOTE]
>
>As Microsoft Edge Webview2 does not save proxy credentials, the Console may ask you to authenticate twice at your first connection.

## Upgrade your client console{#upgrade-ac-console}

When your system is upgraded to a newer release, you must update your client console to that same version. This is a best practice, and for some releases this upgrade is mandatory. In that case, it is mentioned in the [Release Notes](release-notes.md).

As a Managed Cloud Services user, Adobe deploys the client console for you. When you connect to your upgraded environment, you are prompted to download the latest client console version in a pop-up window. You must accept this upgrade, and update the client console as requested.

>[!CAUTION]
>
>Adobe recommends leaving the option **[!UICONTROL No longer ask this question]** unselected to make sure that you are alerted when a new version of the Console is available. If this option is selected, the user is not informed that a Console upgrade is required.
>



## Grant access to users{#grant-access}

Adobe Campaign lets you define and manage the rights assigned to the various operators.

As a Campaign administrator, you are responsible for creating the operators and sharing their credentials with the users. 

Learn more about users and how to define their permissions in [this section](gs-permissions.md).


## Web access{#web-access}

Certain parts of the application can be accessed via a web browser using an HTML user interface: reporting, delivery approval, instance monitoring, and more. 

The Web access provides an interface that is similar to the console but with a reduced set of functionalities.

For example, for a given operator, a campaign will show up with the following options in the console:

![](assets/campaign-from-console.png)

Whereas with Web access, the options will mainly enable viewing:

![](assets/campaign-from-web.png)

Web access is also used to in the validation process: operators can click on the approval request email and connect to Campaign through their web browser to validate or reject a delivery content or budget.

To access to your Campaign instance from the web, the URL is:  `https://<your adobe campaign server>:<port number>/view/home`.
