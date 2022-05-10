---
title: Manage subscriptions and unsubscriptions in Campaign
description: Learn how to manage subscriptions and unsubscriptions in Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d5933b12-8664-49b8-953c-ea98eb428cc2
---
# Manage subscriptions and unsubscriptions{#optin-optout}

Use Adobe Campaign to create and monitor your information services such as newsletters and to manage the subscriptions/unsubscriptions to these services. Several services can be defined in parallel, for example: specialist newsletters for certain product categories, themes or areas of a web site, subscriptions to various types of alert messages and real-time notifications. Refer to Manage subscriptions.

![](../assets/do-not-localize/book.png) Learn how to create an information service, send newsletter and manage opt-in and opti-out in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html){target="_blank"}

To subscribe (opt-in) a profile to a service, available options are:

* Manually add the service to the recipient profile: to do this, from the **[!UICONTROL Subscriptions]** tab of their profile, click **[!UICONTROL Add]** and select the information service concerned. 

   ![](assets/subscribe-to-a-service.png) 
    
   ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target="_blank"}
    
* Automatically subscribe a set of recipients to the service. The list of recipients can come from a filtering operation, a group, a folder, an import, or a direct manual selection. To subscribe these recipients, select the profiles and right-click. Select **[!UICONTROL Actions > Subscribe selection to a service...]**.

   ![](assets/subscribe-selection.png) 

   Select the service concerned, and start the operation.

   ![](assets/subscribe-confirm.png) 

   ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#deliveries-tab){target="_blank"}


* Import recipients and subscribe them automatically to an information service. To do this, select the service concerned in the last step of the import wizard. 

   ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=en#step-5---additional-step-when-importing-recipients){target="_blank"}

* Use a web form so that recipients can subscribe to a service. 

   ![](assets/opt-in-webapp.png) 

   Campaign comes with a default web form to manage opt-in. You can personalize it and map the profile data.

   ![](assets/web-app.png) 

   ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/use-cases--web-forms.html?lang=en#create-a-subscription--form-with-double-opt-in){target="_blank"}


* Create a targeting workflow and using a **[!UICONTROL Subscription service]** activity. 

   ![](assets/wf-subscription.png) 

   ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/subscription-services.html?lang=en#example--subscribe-a-list-of-recipients-to-a-newsletter){target="_blank"}
    
To unsubscribe (opt-out) a profile from a service, available options are:

**Manual unsubscription**

* Personalized unsubscription link or web form
* Manual deletion of an information service
* Manual deletion of recipients from particular subscription service

**Automatic unsubscription**

* Specify a duration limit of the information service: recipients will be unsubscribed automatically when the period of validity has expired. This period is specified in the Edit tab of the service properties. It is expressed in days.
* Set up an unsubscription workflow for a population.

![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/managing-subscriptions.html?lang=en#unsubscribing-a-recipient-from-a-service){target="_blank"}


>[!CAUTION]
>
>In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), subscriptions and unsubscriptions are **asynchronous** processes. Opt-in and opt-out requests are processed each hour. [Learn more](../architecture/new-apis.md#sub-apis)

You can also enable your delivery recipients to forward messages to a friend. To do this, insert the relevant links into your delivery. You may then track this sharing process as well as the number of visits to the concerned pages. 

![](../assets/do-not-localize/book.png) For more on this capability, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/viral-and-social-marketing.html?lang=en#viral-marketing--forward-to-a-friend){target="_blank"}
