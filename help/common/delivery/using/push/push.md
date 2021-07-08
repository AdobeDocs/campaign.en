---
product: Adobe Campaign
title: Send push notification with Adobe Campaign
description: Get started with push notification in Campaign
feature: Overview
role: Data Engineer
level: Beginner
---
# Get started with push notifications

Mobile app deliveries let you send notifications to iOS and Android systems.

To send push notifications in Adobe Campaign, you need to:

1. Configure your Campaign environment
1. Create a Mobile application-type information service for your mobile application. 
1. Add the iOS and Android versions of the application to this service.
1. Create a delivery for both iOS and Android. 

Learn how to get started with mobile app in [this page](about-mobile-app-channel.md).

## Integrate with Adobe SDK

### Integrate Campaign SDK 

Campaign SDK facilitates the integration of your mobile application into the Adobe Campaign platform.

Compatible SDK versions are listed in [Campaign Classic v7 Compatibility matrix](../../../../v7/rn/using/compatibility-matrix.md#MobileSDK) and [Campaign v8 Compatibility matrix](../../../../v8/start/compatibility-matrix.md#MobileSDK).

### Configure Campaign Extension in Launch

You can integrate Adobe Experience Platorm Launch SDK with Campaign, by leveraging Campaign Classic extension.

Learn more in [Adobe Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic){target="_blank"}

## Configure your app settings in Campaign

You must define your iOS and Android apps settings in Adobe Campaign.

Configuration guidelines for iOS are detailed in [this page](configuring-the-mobile-application.md)

Configuration guidelines for Anddroid are detailed in [this page](configuring-the-mobile-application-android.md)

## Create your first push notification

This section details the elements specific to the delivery of iOS and Android notifications.

>[!CAUTION]
>
>With Campaign v8, mobile registration is now **asynchronous**. [Learn more](../../../../v8/dev/staging.md).

To create a new delivery, browse to the **[!UICONTROL Campaigns]** tab, click **[!UICONTROL Deliveries]** and click the **[!UICONTROL Create]** button above the list of existing deliveries.

![](../assets/delivery_step_1.png)

For global information on how to create a delivery, refer to [this section](../steps-about-delivery-creation-steps.md).

### Send notifications on iOS {#send-notifications-on-ios}

1. Select the **[!UICONTROL Deliver on iOS]** delivery template and click **[!UICONTROL Continue]**.

   ![](../assets/push-template-ios.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

   ![](../assets/push-ios-select-target.png)

1. Select **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, select the service relevant to your mobile application, then select the iOS version of the application.

   ![](../assets/push-ios-subscribers.png)

1. Select the notification type: **[!UICONTROL Alert]**, **[!UICONTROL Badge]**, **[!UICONTROL Alert and badge]** or **[!UICONTROL Silent Push]**.

   ![](../assets/push-ios-alert.png)

1. In the **[!UICONTROL Title]** field, enter the label of the title that you want to appear on the notification.

1. Enter the **[!UICONTROL Message]** and the **[!UICONTROL Value of the badge]** based on the chosen notification type.

1. You can also define the following elements:

    * The **[!UICONTROL Action button]** allows you to define a label for the action button appearing on the alert notifications (**action_loc_key** field of the payload).

    * In the **[!UICONTROL Play a sound]** field, select the sound to be played by the mobile terminal when the notification is received.

    * In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   ![](../assets/push-ios-preview.png)


### Send notifications on Android {#send-notifications-on-android}

1. Select the **[!UICONTROL Deliver on Android (android)]** delivery template.

    ![](../assets/push-template-android.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

    ![](assets/push-android-select-target.png)

1. Select **[!UICONTROL Subscribers of an Android mobile application]**, choose the service relevant to your mobile application (Neotrips, in this case), then select the Android version of the application.

   ![](../assets/push-ios-subscribers.png)

1. Then enter the content for the notification.

   ![](../assets/push-android-content.png)

1. Click the **[!UICONTROL Insert emoticon]** icon to insert emoticons to your push notification.

1. In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   <!--![](assets/push-android-preview.png)-->

## Test, send and monitor your push notifications

To send a proof and to send the final delivery, use the same process as email deliveries. Learn more in the pages below:

* [Learn key steps to validate a delivery](../steps-validating-the-delivery.md)

* [Learn key steps to send a delivery](../)steps-sending-the-delivery.md)

After sending messages, you can monitor and track your deliveries. Learn more in the pages below:

* [Learn more about push notification quarantines](../understanding-quarantine-management.md#push-notification-quarantines)

* [Learn how to troubleshoot your push notifications](troubleshooting.md)
