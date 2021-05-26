---
solution: Campaign v8
product: Adobe Campaign
title: Send push notification with Adobe Campaign
description: Get started with push notification in Campaign
feature: Overview
role: Data Engineer
level: Beginner
---
# Create and send push notifications

Mobile app deliveries let you send notifications to iOS and Android systems.

To send push notifications in Adobe Campaign, you need to:

1. Configure your Campaign environment
1. Create a Mobile application-type information service for your mobile application. 
1. Add the iOS and Android versions of the application to this service.
1. Create a delivery for both iOS and Android. 

[!DNL :arrow_upper_right:] Learn how to get started with mobile app in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integrate with Adobe SDK

### Integrate Campaign SDK 

Campaign SDK facilitates the integration of your mobile application into the Adobe Campaign platform.

[!DNL :arrow_upper_right:] Learn how to integrate Campaign SDK with your app in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

[!DNL :arrow_upper_right:] Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configure your app settings in Campaign

You must define your iOS and Android apps settings in Adobe Campaign.

[!DNL :arrow_upper_right:] Configuration guidelines for iOS are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Configuration guidelines for Anddroid are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Create your first push notification

[!DNL :arrow_upper_right:] Learn how to create your first push notifications in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>With Campaign v8 mobile registration is now **asynchronous**. [Learn more](../dev/staging.md).
