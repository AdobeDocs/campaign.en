---
solution: Campaign v8
product: Adobe Campaign
title: Learn how to connect to Campaign v8
description: Connect to Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
---
# Connect to Adobe Campaign v8{#gs-ac-connect}

Campaign Client Console is a rich client which enables you to connect to your Campaign application server(s).

Before starting, you need to:

* Check your system and tools compatibility with Adobe Campaign in the [Compatibility matrix](compatibility-matrix.md)
* Get your Campaign server URL 
* Get your user credentials

## Download and install the Client Console

When using Campaign for the first time, or if you need to upgrade to a newer version, you need to download the Client Console and install it. 

Two options are available:

1. As a Campaign administrator, connect to Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) and download the Client Console installation program. You can then install it on your local machine.

1. As a end-user, Adobe can deploy the Console for you: once the Console is updated, you will be prompted to download the latest Client Console version in a pop-up window. 

>[!CAUTION]
>
>Adobe recommends leaving the option **[!UICONTROL No longer ask this question]** unselected to make sure that all users are alerted when a new version of the Console is available.  If this option is selected the user will not be informed of new available versions.

## Create your connection

Once the Client Console is newly installed, follow the steps below to create the connection to the application server:

1. Start the Console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

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

1. Start the Console from the Windows **[!UICONTROL Start]** menu, in the **Adobe Campaign** program group.

1. Click the link in the top right-hand corner of the credentials fields to access the connection configuration window.

1. Select the Campaign instance you need to log in to.

1. Click **[!UICONTROL Ok]**.

1. Enter your user login credentials and click **[!UICONTROL LOG IN]**.

   ![](assets/sign-in-v8.png) 

Depending on your configuration, your credentials can be:

* provided by your Campaign administrator who granted you access
* your Adobe ID

## Grant access to users

Adobe Campaign lets you define and manage the rights assigned to the various operators. These are a set of rights and restrictions that authorize or deny:

* Access to certain functionalities (via the named rights),
* Access to certain elements,
* Create, modify and/or delete elements (delivery, contacts, campaigns, groups, etc.).

Learn more about users and how to define their permissions in [this section](permissions.md).

As a Campaign administrator, you are responsible for creating the operators and sharing their credentials with the users.

## Connect to Campaign with your Adobe ID{#connect-ims}

Campaign users can connect to the Adobe Campaign console using their Adobe ID, through Adobe Identity Management System (IMS). This implementation provides the following advantages:

* The same ID can be used for all Experience Cloud solutions.
* The connection is memorized when using Adobe Campaign with different integrations.
* Stronger password management policy.
* Use of Federated ID accounts (external ID provider).

:speech_balloon: As a Managed Cloud Services user, [contact Adobe](campaign-faq.md#support) to implement Adobe IMS with Campaign.

## Connect to Campaign with your LDAP login

Adobe Campaign can be configured so that the user accesses the platform via their LDAP authentication. 

:speech_balloon: As a Managed Cloud Services user, [contact Adobe](campaign-faq.md#support) to configure LDAP integration with Campaign.


## Web access{#web-access}

Certain parts of the application can be accessed via a simple web browser using an HTML user interface: Campaign dashboard, Cube reporting, instance monitoring, and more. 

:[!DNL :arrow_upper_right:]: Learn more about Web access in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#console-and-web-access)

Web access is also used to in the validation process: operators can click on the approval request email and connect to Campaign through their web browser to validate or reject a delivery content or budget.

:[!DNL :arrow_upper_right:]: Learn how to set up and manage approvals in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)
