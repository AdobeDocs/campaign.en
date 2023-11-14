---
product: campaign
title: Push Notification Channel upcoming changes
description: Push Notification Channel upcoming changes
hide: yes
hidefromtoc: yes
---
# Push Notification Channel upcoming changes {#push-upgrade}

You can use Campaign to send push notifications on Android devices. To perform this, Campaign relies on specific Android external accounts and subscription services. Some important changes to the Android Firebase Cloud Messaging (FCM) service will be released in 2024, and may impact your Adobe Campaign implementation.

## What changed? {#fcm-changes}

As part of Google's continual effort to improve its services, the legacy FCM APIs will be discontinued on **June 20, 2024**. Learn more about Firebase Cloud Messaging HTTP protocol in [Google documentation](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 and Adobe Campaign v8 already support the latest APIs to send Push Notification Messages. However, some old implementations still rely on the legacy APIs. These implementations must be updated.

## Are you impacted? {#fcm-impact}

If your current implementation supports subscription services connecting to FCM using the legacy APIs, you are impacted. Migration to the latest APIs is mandatory to avoid any service distruption. In that case, Adobe teams will reach out to you.

To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below:

![](assets/filter-services-fcm.png)


* If any of your active push notification campaigns utilize the **HTTP (legacy)** API, your setup will be directly impacted by this change. You must review your current configurations and migrate to the newer APIs as described below.

* If your setup exclusively uses the **HTTP v1** API for Android Push notifications, then you are already in compliance and no further action will be required on your part.

## How to migrate?{#fcm-migration-procedure}

### Prerequisites{#fcm-migration-prerequisites}

* For Campaign Classic v7, the support of HTTP v1 has been added in 20.3.1 release. If your environment is running on an older version, a prerequisite for the migration to HTTP v1 is to upgrade your environment to the [latest Campaign Classic build](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. For Campaign v8, HTTP v1 is supported by all releases. No upgrade is needed.

* To perform the migration, the Android Firebase Admin SDK service's account JSON file is needed to have the mobile application moved to HTTPv1. Refer to this [page](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* For Hybrid, Hosted and Managed Services deployments, contact Adobe to update your Real-Time (RT) execution server. 

### Migration procedure {#fcm-migration-procedure}

To migrate your environment to HTTP v1, follow these steps on your Marketing and Real-Time execution servers:

1. Browse to your list of **Services and Subscriptions**.

1. Locate all mobile applications using the **HTTP (legacy)** API version.

1. For each of these mobile applications, set the **API version** to **HTTP v1**.

1. Click the **[!UICONTROL Load project json file to extract project details...]** link to load directly your JSON key file.

   You can also enter manually the following details:
      * **[!UICONTROL Project Id]**
      * **[!UICONTROL Private Key]**
      * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Click **[!UICONTROL Test the connection]** to check that your configuration is correct and that the marketing server has access to the FCM. Note that for Mid-Sourcing deployments, the **[!UICONTROL Test connection]** button cannot check if the server has access to the Android Firebase Cloud Messaging (FCM) service.

1. As an option, you can enrich a push message content with some **[!UICONTROL Application variables]** if needed. These are fully customizable and a part of the message payload sent to the mobile device. 

1. Click **[!UICONTROL Finish]** then **[!UICONTROL Save]**. 

Below are the FCM payload names to further personalize your push notification:

| Message type | Configurable message element (FCM payload name) |  Configurable options (FCM payload name) |
|:-:|:-:|:-:|
| data message  | N/A  | validate_only  |
| notification message |  title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>The switch to HTTP v1 API is applied to all new deliveries. Deliveries in retry, in progress, and in use still use the HTTP (legacy) API.

### Android OS and Android Mobile Application

There are no specific changes required to the Android Mobile applications' code and the notification behavior should not change.


However, with HTTP v1, you can further personalize your push notification with **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)


   * Use the **[!UICONTROL Ticker]** field to set the ticker text of your notification.
   * Use the **[!UICONTROL Image]** field to set the image's URL to be displayed in your notification.
   * Use the **[!UICONTROL Notification Count]** field to set the number of new unread information to display directly on the application icon.
   * Set the **[!UICONTROL Sticky]** option to false so that the notification is automatically dismissed when the user clicks it. If set to true, the notification is still displayed even when the user clicks it.
   * Set the **[!UICONTROL Notification Priority]** level of your notification to default, minimum, low or high. 
   * Set the **[!UICONTROL Visibility]** level of your notification to public, private or secret. 

   For more on the **[!UICONTROL HTTP v1 additional options]** and how to fill these fields, refer to [FCM documentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

