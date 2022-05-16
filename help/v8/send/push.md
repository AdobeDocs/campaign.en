---
title: Send push notification with Adobe Campaign
description: Get started with push notification in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
---
# Create and send push notifications

Mobile app deliveries let you send notifications to iOS and Android systems.

To send push notifications in Adobe Campaign, you need to:

1. Configure your Campaign environment
1. Create a Mobile application-type information service for your mobile application. 
1. Add the iOS and Android versions of the application to this service.
1. Create a delivery for both iOS and Android. 

![](../assets/do-not-localize/book.png) Learn how to get started with mobile app in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html){target="_blank"}

## Integrate Campaign SDK 

Campaign SDK facilitates the integration of your mobile application into the Adobe Campaign platform.

Compatible SDK versions are listed in [Campaign Compatibility matrix](../start/compatibility-matrix.md#MobileSDK).

![](../assets/do-not-localize/glass.png) Learn how to integrate Campaign Android and iOS SDKs with your app in [this section](../config/push-config.md)

<!--
### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

![](../assets/do-not-localize/book.png) Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

--> 

## Configure your app settings in Campaign

You must define your iOS and Android apps settings in Adobe Campaign.

![](../assets/do-not-localize/book.png) Configuration guidelines for iOS are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages){target="_blank"}

![](../assets/do-not-localize/book.png) Configuration guidelines for Anddroid are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages){target="_blank"}

## Create your first push notification

This section details the elements specific to the delivery of iOS and Android notifications.

>[!CAUTION]
>
>With Campaign v8, mobile registration is now **asynchronous**. [Learn more](../dev/staging.md)

To create a new delivery, browse to the **[!UICONTROL Campaigns]** tab, click **[!UICONTROL Deliveries]** and click the **[!UICONTROL Create]** button above the list of existing deliveries.

![](assets/delivery_step_1.png)

![](../assets/do-not-localize/book.png) For global information on how to create a delivery, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target="_blank"}

### Send notifications on iOS {#send-notifications-on-ios}

1. Select the **[!UICONTROL Deliver on iOS]** delivery template and click **[!UICONTROL Continue]**.

   ![](assets/push-template-ios.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

   ![](assets/push-ios-select-target.png)

1. Select **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, select the service relevant to your mobile application, then select the iOS version of the application.

   ![](assets/push-ios-subscribers.png)

1. Select the notification type: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** or **[!UICONTROL Silent Push]**.

   ![](assets/push-ios-alert.png)

1. In the **[!UICONTROL Title]** field, enter the label of the title that you want to appear on the notification.

1. Enter the **[!UICONTROL Message]** and the **[!UICONTROL Value of the badge]** based on the chosen notification type.

1. You can also define the following elements:

    * The **[!UICONTROL Action button]** allows you to define a label for the action button appearing on the alert notifications (**action_loc_key** field of the payload).

    * In the **[!UICONTROL Play a sound]** field, select the sound to be played by the mobile terminal when the notification is received.

    * In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   ![](assets/push-ios-preview.png)


### Send notifications on Android {#send-notifications-on-android}

1. Select the **[!UICONTROL Deliver on Android (android)]** delivery template.

    ![](assets/push-template-android.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

    ![](assets/push-android-select-target.png)

1. Select **[!UICONTROL Subscribers of an Android mobile application]**, choose the service relevant to your mobile application (Neotrips, in this case), then select the Android version of the application.

   ![](assets/push-ios-subscribers.png)

1. Then enter the content for the notification.

   ![](assets/push-android-content.png)

1. Click the **[!UICONTROL Insert emoticon]** icon to insert emoticons to your push notification.

1. In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   <!--![](assets/push-android-preview.png)-->

## Test, send and monitor your push notifications

To send a proof and to send the final delivery, use the same process as email deliveries. Learn more in Campaign Classic v7 documentation:

* Validate a delivery and send proofs
   ![](../assets/do-not-localize/book.png) [Learn key steps to validate a delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target="_blank"}

* Confirm and send the delivery
    ![](../assets/do-not-localize/book.png) [Learn key steps to send a delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en){target="_blank"}

After sending messages, you can monitor and track your deliveries. Learn more in Campaign Classic v7 documentation:

* Push notification quarantines
    ![](../assets/do-not-localize/book.png) [Learn more about push notification quarantines](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=en#push-notification-quarantines){target="_blank"}

* Troubleshooting
    ![](../assets/do-not-localize/book.png) [Learn how to troubleshoot your push notifications](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=en){target="_blank"}
