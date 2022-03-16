---
title: Work with Campaign and Twitter
description: Learn how to integrate your Campaign environment with Twitter
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: yes
hide: yes
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
---
# Work with Campaign and Twitter{#tw-ac-ovv}

The **Managing social networks (Social Marketing)** module lets you interact with your customers via Twitter. Use this capability to:

* Send messages - Use Adobe Campaign Social Marketing to post messages on Twitter. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to connect Campaign with Twitter. The  **Managing social networks (Social Marketing)** module must be installed on your environment, through the dedicated package.


To configure Adobe Campaign to post tweets to your Twitter accounts, delegate write access to Adobe Campaign for these accounts. To do this:

1. Create a Twitter account
1. Create a test Twitter account for sending proofs
1. Create a Twitter application (one app per Twitter account)
1. Create a new service for **[!UICONTROL Twitter]** (one service per Twitter account)

## Create a test account on Twitter {#tw-test-account}

In addition to Twitter account, create a private Twitter account which can be used for sending [tweet proofs](../send/twitter.md#send-proofs). To do this, follow the steps below:

1. Create a new Twitter account.
1. Access the account  **Settings**.
1. Browse to **Privacy & Safety** and **Audience and Tagging** and check the **Protect your Tweets** option. Your Tweets and other account information are only visible to people who follow you.

![](assets/social_tw_test_page.png)

## Create an application on Twitter {#create-an-app-on-twitter}

Create a Twitter application to enable Adobe Campaign to post tweets to your Twitter account.  To do this, follow the steps below:

1. Log on to your Twitter account.
1. Connect to [Twitter developer portal](https://developer.twitter.com/en/apps).
1. Select **Create an App**.
1. Let Twitter assistant guide you through the process.

   To allow Adobe Campaign to post tweets to your account, edit to the **Permissions** tab of the application and select **Read and Write** for the **Access** section. In the **Settings** tab, you also need to leave the **Callback URL** field empty.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>You need one application per Twitter account. As a consequence, you must create another test application to send proofs to your test account.
>

## Create a Twitter service in Campaign {#create-tw-service}

Create a **Twitter** service in Campaigna and delegate write access to Campaign. This new service is used to link your Campaign instance with your Twitter account.

To enter settings, you must access to your Adobe Campaign console and an your Twitter account:

1. Open **Twitter**, and from [the Project and Apps page](https://developer.twitter.com/en/portal/projects-and-apps), select the app created previously. Access the **App Permissions**.

  ![](assets/social_tw_service.png)

   Edit the **Keys and tokens** tab to access your app details.

1. In **Adobe Campaign**, browse to the **[!UICONTROL Profiles and targets]** tab, and select the **[!UICONTROL Services and Subscriptions]** link
1. Create a new service.
1. Select the **[!UICONTROL Twitter]** type.

   >[!NOTE]
   >
   >The **[!UICONTROL Synchronize subscriptions]** option is enabled by default: this option recovers automatically the list of your Twitter followers so that you can [send them direct messages](../send/twitter.md#send-direct-messages). Synchronization is performed by a [dedicated technical workflow](#synchro-tw-accounts). 

1. Enter the label and internal name of the service.

   >[!CAUTION]
   >
   >The **[!UICONTROL Internal name]** of the service must be the exact same name of your Twitter account. To check your settings, you can:

    * Click the **[!UICONTROL Save]** button.
    * In the overview of services, select the **Twitter** service which you have just created.
    * Browse the **[!UICONTROL Twitter page]** tab: your Twitter account should be displayed. 

1. By default, followers are saved in the **[!UICONTROL Visitors]** folder. You can select another location from the **[!UICONTROL Visitor folder]** field. [Learn more](../send/twitter.md#operating-principle)

1. From your Twitter app, copy the content of the **[!UICONTROL Consumer Key (API Key)]** and **[!UICONTROL Consumer Secret (API Secret)]** fields and paste them into the **[!UICONTROL Consumer key]** and **[!UICONTROL Consumer secret]** fields of your Campaign **Twitter** service.

1. From your Twitter app, copy the content of the **[!UICONTROL Access Token]** and **[!UICONTROL Access Token Secret]** fields and paste them into the **[!UICONTROL Access token]** and **[!UICONTROL Access token secret]** fields of your Campaign **Twitter** service.

1. In Campaign client console, click **[!UICONTROL Save]**. You have now delegated write access to Adobe Campaign.


>[!NOTE]
>
>Create one **Twitter** service per Twitter account. As a consequence, you must create another test service to send proofs to your test account.
>

## Synchronize your Twitter account {#synchro-tw-accounts}

The **[!UICONTROL Twitter account synchronization]** technical workflow synchronizes Twitter accounts in Adobe Campaign.  

This workflow is accessed via the **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** node. By default, this workflow is triggered every Thursday at 7:30AM.

You can use the **[!UICONTROL Execute pending task(s) now]** option to start the workflow at any time as you are implementing this integration. 

You can also edit the scheduler to change the workflow triggering frequency. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target="_blank"}.

>[!CAUTION]
>
>To recover the list of Twitter subscribers, the **[!UICONTROL Twitter account synchronization]** option must be checked for the service linked to the account. [Learn more](#create-tw-service)

You may now post tweets to your Twitter accounts and direct messages to your followers. For more on this, refer to [this page](../send/twitter.md).
