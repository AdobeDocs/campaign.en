---
title: Integrate AEP SDK and Campaign 
description: Learn how to integrate Adobe Experience Platform mobile SDK with your app
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: yes
hidefromtoc: yes
---

# AEP SDK + Campaign: configure push notification channel {#push-notification-configuration}

Before beginning to send push notifications with Adobe Campaign, you need to ensure configurations and integrations are in place on the mobile app and for tags in Adobe Experience Platform.

Adobe Experience Platform Mobile SDK provides client-side integration APIs for your mobiles via Android and iOS compatible SDKs. 

To set up your app with Adobe Experience Platform Mobile SDKs, follow these steps:

1. Check [prerequisites](#before-starting).
1. Set up a [mobile tag property](#launch-property) in Adobe Experience Platform Data Collection.
1. Get the Adobe Experience Platform Mobile SDK as detailed [in this page](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (optional) Enable logging and lifecycle metrics, as detailed [in this page](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (optional) Add [Adobe Experience Platform Assurance to your app](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Follow [Adobe Experience Platform Mobile SDK documentation](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} to get setup with Adobe Experience Platform Mobile SDKs in your app.
1. Install and configure [Adobe Campaign Extension](#configure-extension) in your mobile property.
1. Configure your iOS and Android mobile services in Adobe Campaign as detailed [in this page](../send/push.md#push-config).


## Prerequisites {#before-starting}

### Set up permissions {#setup-permissions}

Before creating a mobile application, you first need to make sure that you have or assign the correct user permissions for tags in Adobe Experience Platform. User permissions for tags in Adobe Experience Platform are assigned to users through Adobe Admin Console. Learn more in [Tags documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>Push configuration must be performed by an expert user. Depending on your implementation model and personas involved in this implementation, you might need to assign the full set of permissions to a single product profile or share permissions between the app developer and the **Adobe Campaign** administrator. 

To assign **Property** and **Company** rights, follow the steps below:

1. Access the **[!DNL Admin Console]**.
1. From the **[!UICONTROL Products]** tab, select the **[!UICONTROL Adobe Experience Platform Data Collection]** card.
1. Select an existing **[!UICONTROL Product Profile]** or create a new one with the **[!UICONTROL New profile]** button. Learn how to create a new **[!UICONTROL New profile]** in the [Admin console documentation](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. From the **[!UICONTROL Permissions]** tab, select **[!UICONTROL Property Rights]**.
1. Click **[!UICONTROL Add all]**. This will add the following right to your product profile:
    * **[!UICONTROL Approve]**
    * **[!UICONTROL Develop]**
    * **[!UICONTROL Edit Property]**
    * **[!UICONTROL Manage Environments]**
    * **[!UICONTROL Manage Extensions]**
    * **[!UICONTROL Publish]**

    These permissions are required to install and publish the Adobe Campaign extension, and publish the app property in **Adobe Experience Platform Mobile SDK**.

1. Then, select **[!UICONTROL Company rights]** in the left-hand menu.
1. Add the following rights:

    * **[!UICONTROL Manage App Configurations]**
    * **[!UICONTROL Manage Properties]**

    These permissions are required for the mobile app developer to set up push credentials in **Adobe Experience Platform Data Collection**.

1. Click **[!UICONTROL Save]**.

To assign this **[!UICONTROL Product profile]** to users, follow the steps below:

1. Access the **[!DNL Admin Console]**.
1. From the **[!UICONTROL Products]** tab, select the **[!UICONTROL Adobe Experience Platform Data Collection]** card.
1. Select your previously configured **[!UICONTROL Product profile]**.
1. From the **[!UICONTROL Users]** tab, click **[!UICONTROL Add user]**.
1. Type in your user's name or email address and select the user. Then, click **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >If the user was not previously created in the Admin console, refer to the [Add users documentation](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configure your app {#configure-app}

The technical setup involves close collaboration between the app developer and business administrator. Before starting sending push notifications with [!DNL Adobe Campaign], you need to define settings in [!DNL Adobe Experience Platform Data Collection] and integrate your mobile app with Adobe Experience Platform Mobile SDKs. 

Follow implementation steps detailed in the links below:

* For **Apple iOS**: Learn how to register your app with APNs in [Apple Documentation](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* For **Google Android**: Learn how to setup up a Firebase Cloud Messaging client app on Android in [Google Documentation](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Set up a mobile tag property in Adobe Experience Platform Data Collection {#launch-property}

Setting up a mobile property allows the mobile app developer or marketer to configure the mobile SDKs. You will typically create a mobile property for each mobile application you want to manage. Learn how to create and configure a mobile property in [Adobe Experience Platform Mobile SDK documentation](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.

Learn more about [!DNL Adobe Experience Platform Data Collection] tags in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Once created, open the new tag property and create a library. To do this:

1. Browse to **Publishing Flow** in the left navigation and select **Add Library**. 
1. Enter the name of the library and select the environment.
1. Select **Add All Changed Resources**, and **Save and Build to development**.
1. Finally, set this library as your working library from the **Select a working library** button.


## Configure Adobe Campaign Extension in your mobile property {#configure-extension}

The **Adobe Campaign Classic extension** for Adobe Experience Platform Mobile SDKs powers push notifications for your mobile apps and helps you collects user push tokens and manages interaction measurement with Adobe Experience Platform services.

This extension is pre-installed on your environment and must be configured. To configure the extension for your mobile tag property, follow these steps:

1. Open the tag property you created before.
1. From the left navigation, browse to **Extensions**, and open the **Catalog** tab. Use the search field to find the **Adobe Campaign Classic** extension.
1. From the Campaign Classic card, click the **Install** button.
1. Enter settings as described in [Adobe Experience Platform Mobile SDK documentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

You can now add Campaign to your app, as detailed in  [Adobe Experience Platform Mobile SDK documentation](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configure your mobile services in Campaign{#push-service}

Once your mobile app has been set up in in [!DNL Adobe Experience Platform Data Collection], you need to create two services (one for iOS devices, one for Android devices) to be able to send push notifications from **[!DNL Adobe Campaign]**.

Learn how to create and configure a service for iOS and Android push notifications in [this section](../send/push.md#push-config).
