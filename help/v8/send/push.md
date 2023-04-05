---
title: Send push notification with Adobe Campaign
description: Get started with push notification in Campaign
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
---
# Create and send push notifications{#push-notifications-create}

Mobile app deliveries let you send notifications to iOS and Android devices.

To send push notifications in Adobe Campaign, you need to:

1. Integrate the SDK with your app. [Learn more](#push-sdk)
1. Create a Mobile application-type information service for your mobile application, and add the iOS and Android versions of the application to that service. [Learn more](#push-config)
1. Create a delivery for both iOS and Android. [Learn more](#push-create)

## Integrate the SDK {#push-sdk}

You can use the Adobe Experience Platform Mobile SDK by configuring the Adobe Campaign extension in the Data Collection UI. The Adobe Experience Platform Mobile SDK helps power Adobe's Experience Cloud solutions and services in your mobile apps. SDKs configuration is managed through the Data Collection UI for flexible configuration and extensible, rules-based integrations. [Learn more in Adobe Developer documentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

You can also integrate Campaign SDK to facilitate the integration of your mobile application into the Adobe Campaign platform. Compatible SDK versions are listed in [Campaign Compatibility matrix](../start/compatibility-matrix.md#MobileSDK).

Learn how to integrate Campaign Android and iOS SDKs with your app in [this page](../config/push-config.md)

## Configure your app settings in Campaign{#push-config}

Before sending push notifications, you must define your iOS and Android apps settings in Adobe Campaign.

Push notifications are sent to your app users through a dedicated service. When users install your app, they subscribe to this service: Adobe Campaign relies on this service to target only the subscribers of your app. In this service, you need to add your iOS and Android apps to send on iOS and Android devices.

To create a service to send push notifications, follow the steps below:

1. Browse to **[!UICONTROL Profiles and Targets > Services and Subscriptions]** tab, and click **[!UICONTROL Create]**.

   ![](assets/new-service-push.png){width="800" align="left"}

1. Enter a **[!UICONTROL Label]** and an **[!UICONTROL Internal name]**, and select a **[!UICONTROL Mobile application]** type.

   >[!NOTE]
   >
   >The default **[!UICONTROL Subscriber applications (nms:appSubscriptionRcp)]** target mapping is linked to the recipients table. If you want to use a different target mapping, you need to create a new target mapping and enter it in the **[!UICONTROL Target mapping]** field of the service. Learn more about target mappings in [this page](../audiences/target-mappings.md).

1. Then use the **[!UICONTROL Add]** icon on the right to define the mobile applications that use this service.

>[!BEGINTABS]

>[!TAB iOS]

To create an app for iOS devices, follow these steps:

1. Select **[!UICONTROL Create an iOS application]** and click **[!UICONTROL Next]**.

   ![](assets/new-ios-app.png){width="600" align="left"}

1. Enter the name of your app in the **[!UICONTROL Label]** field.
1. (optional) You can enrich a push message content with some **[!UICONTROL Application variables]**. These are fully customizable and a part of the message payload sent to the mobile device.

   In the example bellow, the **mediaURl** and **mediaExt** variables are added to create rich push notification and then provides the application with the image to display within the notification.

   ![](assets/ios-app-parameters.png){width="600" align="left"}

1. Browse to the **[!UICONTROL Subscription parameters]** tab to define the mapping with an extension of the **[!UICONTROL Subscriber applications (nms:appsubscriptionRcp)]** schema.

1. Browse to the **[!UICONTROL Sounds]** tab to define a sound to play. Click **[!UICONTROL Add]** and fill **[!UICONTROL Internal name]** field which must contain the name of the file embedded in the application or the name of the system sound.

1. Click **[!UICONTROL Next]** to start configuring the development application.

1. The integration key is specific to each application. It links the mobile application to Adobe Campaign.

   Make sure that the same **[!UICONTROL Integration key]** is defined in Adobe Campaign and in the application code via the SDK. 

   If you are using Campaign SDK, learn more in[this page](../config/push-config.md). 
   
   
   If you are using Adobe Experience Platform SDK (Data Collection), learn more in [this page](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}
   

    >[!NOTE]
    >
    > The **[!UICONTROL Integration key]** is fully customizable with string value but needs to be exactly the same as the one specified in the SDK.
    >
    > You cannot use the same certificate for the development version (sandbox) and the production version of the application.

1. Select the icon from the **[!UICONTROL Application icon]** field to personalize mobile application in your service.

1. Select the **[!UICONTROL Authentication mode]**. Two modes are available:

   * (Recommended) **[!UICONTROL Token-based authentication]**: Fill in the APNs connection settings **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** and **[!UICONTROL Bundle Id]** then select your p8 certificate by clicking **[!UICONTROL Enter the private key...]**. For more on **[!UICONTROL Token-based authentication]**, refer to [Apple documentation](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_token-based_connection_to_apns){target="_blank"}.
   
   * **[!UICONTROL Certificate-based authentication]**: Click **[!UICONTROL Enter the certificate...]**  then select your p12 key and enter the password that was provided by the mobile application developer.

   You can change your authentication mode later on in the **[!UICONTROL Certificate]** tab of your mobile application.

1. Use the **[!UICONTROL Test the connection]** button to validate your configuration.

1. Click **[!UICONTROL Next]** to start configuring the production application and follow the same steps as detailed above.

1. Click **[!UICONTROL Finish]**.

Your iOS application is now ready to be used in Campaign.

>[!TAB Android]

To create an app for Android devices, follow these steps:

1. Select **[!UICONTROL Create an Android application]** and click **[!UICONTROL Next]**.

   ![](assets/new-android-app.png){width="600" align="left"}

1. Enter the name of your app in the **[!UICONTROL Label]** field.
1. The integration key is specific to each application. It links the mobile application to Adobe Campaign.

   Make sure that the same **[!UICONTROL Integration key]** is defined in Adobe Campaign and in the application code via the SDK. 

   If you are using Campaign SDK, learn more in [this page](../config/push-config.md). 
   
   If you are using Adobe Experience Platform SDK (Data Collection), learn more in [this page](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}
   

    >[!NOTE]
    >
    > The **[!UICONTROL Integration key]** is fully customizable with string value but needs to be exactly the same as the one specified in the SDK.
    >

1. Select the icon from the **[!UICONTROL Application icon]** field to personalize mobile application in your service.
1. Select **HTTP v1** in  **[!UICONTROL API version]** drop-down list. 
1. Click **[!UICONTROL Load project json file to extract project details...]** link to load your JSON key file. For more information on how to extract your JSON file, refer to [Google Firebase documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

   You can also enter manually the following details:
      * **[!UICONTROL Project Id]**
      * **[!UICONTROL Private Key]**
      * **[!UICONTROL Client Email]**

1. Use the **[!UICONTROL Test the connection]** button to validate your configuration.

   >[!CAUTION]
   >
   >The **[!UICONTROL Test connection]** button does not check if the MID server has access to the FCM server.

1. (optional) You can enrich a push message content with some **[!UICONTROL Application variables]** if needed. These are fully customizable and a part of the message payload sent to the mobile device.

1. Click **[!UICONTROL Finish]** then **[!UICONTROL Save]**. Your Android application is now ready to be used in Campaign.

Below are the FCM payload names to further personalize your push notification:

| Message type | Configurable message element (FCM payload name) |  Configurable options (FCM payload name) |
|:-:|:-:|:-:|
| data message  | N/A  | validate_only  |
| notification message |  title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!ENDTABS]


## Create your first push notification{#push-create}

This section details the elements specific to the delivery of iOS and Android notifications.

>[!CAUTION]
>
>In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), mobile registration is now **asynchronous**. [Learn more](../architecture/staging.md)

To create a new delivery, browse to the **[!UICONTROL Campaigns]** tab, click **[!UICONTROL Deliveries]** and click the **[!UICONTROL Create]** button above the list of existing deliveries.

![](assets/delivery_step_1.png)

>[!BEGINTABS]

>[!TAB iOS]

To send notifications on iOS devices, follow these steps:

1. Select the **[!UICONTROL Deliver on iOS]** delivery template.

   ![](assets/push_ios_1.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

   ![](assets/push_ios_2.png)

1. Select **[!UICONTROL Subscribers of an iOS mobile application (iPhone, iPad)]**, select the service relevant to your mobile application, then select the iOS version of the application.

   ![](assets/push_ios_3.png)

1. Choose your **[!UICONTROL Notification type]** between **[!UICONTROL General notification (Alert, Sound, Badge)]** or **[!UICONTROL Silent notification]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >The **Silent Push** mode allows a "silent" notification to be sent to a mobile application. The user is not made aware of the notification's arrival. It is transferred directly to the application.

1. In the **[!UICONTROL Title]** field, enter the label of the title that you want to appear in the list of notifications available from the notification center. 

   This field allows you to define the value of the **title** parameter of the iOS notification payload.

1. You can add a **[!UICONTROL Subtitle]**, value of the **subtitle** parameter of the iOS notification payload.

1. Enter the content of the message in the **[!UICONTROL Message content]** section of the wizard.

1. From the **[!UICONTROL Sound and Badge]** tab, you can edit the following options:

   * **[!UICONTROL Clean Badge]**: enable this options to refresh the badge value.

   * **[!UICONTROL Value]**: set a number which will be used to display directly on the application icon the number of new unread information.

   * **[!UICONTROL Critical alert mode]**: enable this option to add sound to your notification even the user's phone is set on focus mode or if the iPhone is muted.

   * **[!UICONTROL Name]**: select the sound to be played by the mobile terminal when the notification is received.

   * **[!UICONTROL Volume]**: volume of your sound from 0 to 100.

      >[!NOTE]
      > 
      >Sounds must be included in the application and defined when the service is created. 
      >

   ![](assets/push_ios_5.png)

1. From the **[!UICONTROL Application variables]** tab, your **[!UICONTROL Application variables]** are automatically added. They let you define notification behavior, for instance, you can configure a specific application screen to be displayed when the user activates the notification.

1. From the **[!UICONTROL Advanced]** tab, you can edit the following general options:

   * **[!UICONTROL Mutable content]**: enable this option to allow the mobile application to download media content.

   * **[!UICONTROL Thread-id]**: identifier used to group related notifications together.

   * **[!UICONTROL Category]**: name of your category ID which will display action buttons. These notifications give the user a faster way to perform different tasks in response to a notification without opening or navigating in the application.

   ![](assets/push_ios_6.png)

1. For time sensitive notification, you can specify the following options:

   * **[!UICONTROL Target content ID]**: identifier used to target which application window to brought forward when the notification is opened.

   * **[!UICONTROL Launch image]**: name of the launch image file to display. If the user chooses to launch your application, the selected image will displayed instead of your application's launch screen.

   * **[!UICONTROL Interruption level]**:

      * **[!UICONTROL Active]**: Set by default, the system presents the notification immediately, lights up the screen, and can play a sound. Notifications do not break through Focus modes.

      * **[!UICONTROL Passive]**: The system adds the notification to the notification list without lighting up the screen or playing a sound. Notifications do not break through Focus modes.

      * **[!UICONTROL Time sensitive]** The system presents the notification immediately, lights up the screen, can play a sound and break through Focus modes. This level does not require a special permission from Apple.

      * **[!UICONTROL Critical]** The system presents the notification immediately, lights up the screen, and bypasses the mute switch or focus modes. Note that this level requires a special permission from Apple.

   * **[!UICONTROL Relevance score]**: set a relevance score from 0 to 100. The system uses this to sort the notifications in the notification summary.

   ![](assets/push_ios_7.png)

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   ![](assets/push-ios-preview.png)


>[!TAB Android]

To send notifications on Android devices, follow these steps:

1. Select the **[!UICONTROL Deliver on Android (android)]** delivery template.

    ![](assets/push-template-android.png)

1. To define the target of the notification, click the **[!UICONTROL To]** link, then click **[!UICONTROL Add]**.

    ![](assets/push-android-select-target.png)

1. Select **[!UICONTROL Subscribers of an Android mobile application]**, choose the service relevant to your mobile application (Neotrips, in this case), then select the Android version of the application.

   ![](assets/push-android-subscribers.png)

1. Then enter the content for the notification.

   ![](assets/push-android-content.png)

1. Click the **[!UICONTROL Insert emoticon]** icon to insert emoticons to your push notification.

1. In the **[!UICONTROL Application variables]** field, enter the value of each variable. For example, you can configure a specific application screen to be displayed when the user activates the notification.

1. Once the notification is configured, click the **[!UICONTROL Preview]** tab to preview the notification. 

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Test, send and monitor your push notifications

To send a proof and to send the final delivery, use the same process as email deliveries. 

Learn how to validate a delivery in [this page](preview-and-proof.md).

Learn how to confirm and send the delivery in [this page](send.md)

After sending messages, you can monitor and track your deliveries. Learn more in these sections:

* [Push notification quarantines](quarantines.md)
* [Push notification delivery failure reasons](delivery-failures.md#push-error-types)

