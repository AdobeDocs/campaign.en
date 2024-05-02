---
audience: end-user
title: Design a rich push notification delivery
description: Learn how to design an Android rich push notification delivery with Adobe Campaign Web
feature: Push
role: User
level: Beginner
exl-id: 42e3623b-b401-4fcc-80a7-ea38347fddc6
---
# Design an Android rich push delivery {#rich-push}

>[!AVAILABILITY]
>
>This feature is in **Limited Availability** (LA).

With Firebase Cloud Messaging, you can choose between two types of messages:

* The **[!UICONTROL Data message]** is handled by the client app. These messages are sent directly to the mobile application, which generates and displays an Android notification on the device. Data messages contain only your custom application variables.

* The **[!UICONTROL Notification message]**, handled automatically by the FCM SDK. FCM automatically displays the message on your users' devices on behalf of the client app. Notification messages contain a predefined set of parameters and options but can still be further personalized with custom application variables.

## Define the content of the notification {#push-message}

Once your push delivery is created, you can define its content. Three templates are available:

* **Default Template** allows you to send notifications with a simple icon and an accompanying image.

* **Basic Template** can include text, images, and buttons in your notifications.

* **Carousel Template** enables you to send notifications with text and multiple images that users can swipe through.

Browse the tabs below to learn how to compose your message for each templates.

>[!BEGINTABS]

>[!TAB Default template]

1. From the **[!UICONTROL Notification type]** drop-down, select **[!UICONTROL Default]**.

    ![](assets/rich_push_default.png)

1. To compose your message, enter your text in the **[!UICONTROL Title]** and **[!UICONTROL Message]** fields.

    ![](assets/rich_push_default_2.png)

1. Use dynamic personalization fields to define content, personalize data and add dynamic content. [Learn more](../send/personalize.md)

1. To further personalize your push notification, configure the **[!UICONTROL Notification options]** and **[!UICONTROL HTTPv1 additional options]** of your push notification. [Learn more](#push-advanced)

    ![](assets/rich_push_default_3.png)

Once you have defined your message content, you can use test subscribers to preview and test the message.

>[!TAB Basic template]

1. From the **[!UICONTROL Notification Type]** drop-down, select **[!UICONTROL Basic]**.

    ![](assets/rich_push_basic.png)

1. To compose your message, enter your text in the **[!UICONTROL Title]**, **[!UICONTROL Message]** and **[!UICONTROL Expanded message]** fields. 

    The **[!UICONTROL Message]** text appears in the collapsed view while the **[!UICONTROL Expanded message]** is displayed when the notification is expanded.

    ![](assets/rich_push_basic_2.png)

1. Use dynamic personalization fields to define content, personalize data and add dynamic content. [Learn more](../send/personalize.md)

1. Under the **[!UICONTROL Color options]** menu, enter the hexadecimal color codes for your **[!UICONTROL Title]**, **[!UICONTROL Message]** and **[!UICONTROL Background]**.

1. Add a **[!UICONTROL Remind later button]** if needed. Enter your **[!UICONTROL Reminder Text]** and **Date** in the corresponding fields. 

    The **[!UICONTROL Reminder Date]** field expects a value representing an epoch in seconds.

1. Click **[!UICONTROL Add button]** and fill in the following fields:

    * **[!UICONTROL Label]**: Text displayed on the button.
    * **[!UICONTROL Link URI]**: Specify the URI to be executed upon clicking the button.

   You have the option to include up to three buttons in your push notification. If you opt for the **[!UICONTROL Remind later button]**, you can only include a maximum of two buttons.

1. Select the **[!UICONTROL Link type]** of your button's linked URL:

    * **[!UICONTROL Web URL]**: Web URLs direct users to online content. Upon clicking, they prompt the device's default web browser to open and navigate to the designated URL.

    * **[!UICONTROL Deeplink]**: Deep links are URLs guiding users to specific sections within an app even if the app is closed. When clicked, a dialog can appear, allowing users to choose from various apps capable of handling the link.

    * **[!UICONTROL Open App]**: Open App URLs allow you to directly connect to content within an application. It enables your application to establish itself as the default handler for a specific type of link, bypassing the disambiguation dialog. 

    For more information on how to handle Android App Links, refer to [Android Developers documentation](https://developer.android.com/training/app-links).

    ![](assets/rich_push_basic_3.png)

1. To further personalize your push notification, configure the **[!UICONTROL Notification options]** and **[!UICONTROL HTTPv1 additional options]** of your push notification. [Learn more](#push-advanced)

    ![](assets/rich_push_basic_4.png)

Once you have defined your message content, you can use test subscribers to preview and test the message.

>[!TAB Carousel template]

1. From the **[!UICONTROL Notification Type]** drop-down, select **[!UICONTROL Carousel]**.

    ![](assets/rich_push_carousel.png)

1. To compose your message, enter your text in the **[!UICONTROL Title]**, **[!UICONTROL Message]** and **[!UICONTROL Expanded message]** fields. 

    The **[!UICONTROL Message]** text appears in the collapsed view while the **[!UICONTROL Expanded message]** is displayed when the notification is expanded.

    ![](assets/rich_push_carousel_1.png)

1. Use the Expression editor to define content, personalize data and add dynamic content. [Learn more](../send/personalize.md)

1. Under the **[!UICONTROL Color options]** menu, enter the hexadecimal color codes for your **[!UICONTROL Title]**, **[!UICONTROL Message]** and **[!UICONTROL Background]**.

1. Choose how the **[!UICONTROL Carousel]** is operated: 

    * **[!UICONTROL Auto]**: automatically cycles through images as slides, transitioning at predefined intervals.
    * **[!UICONTROL Manual]**: allows users to manually swipe between slides to navigate through the images.     

1. From the **[!UICONTROL Layout]** drop-down, select **[!UICONTROL Filmstrip]** option to include previews of the previous and next images alongside the main slide.

1. Click **[!UICONTROL Add image]** and enter your image URL, Text and Action URL.

    Ensure that you include a minimum of three images and a maximum of five images.

    ![](assets/rich_push_carousel_2.png)

1. To further personalize your push notification, configure the **[!UICONTROL Notification options]** and **[!UICONTROL HTTPv1 additional options]** of your push notification. [Learn more](#push-advanced)

    ![](assets/rich_push_carousel_3.png)

Once you have defined your message content, you can use test subscribers to preview and test the message.

>[!ENDTABS]

## Push notification advanced settings {#push-advanced}

### Notification options {#notification-options}

|Parameter | Description |
|---------|---------|
|**[!UICONTROL Channel ID]** |Set your notification's channel ID. The app must create a channel with this channel ID before any notification with this channel ID is received. |
|**[!UICONTROL Icon]** | Set the notification's icon to display on your profiles' devices. |
|**[!UICONTROL Sound]**| Set the sound to play when the device receives your notification.|
|**[!UICONTROL Tag]**| Set an identifier used to replace existing notifications in the notification drawer. This helps prevent the accumulation of multiple notifications and ensures that only the latest relevant notification is displayed.|
|**[!UICONTROL Color]**|Set your notification's icon color with hexadecimal color code.|
|**[!UICONTROL Click action]** | Set the action associated with a user click on your notification.|
|**[!UICONTROL Notification background color]**| Set the color of your Notification background with your Hex color codes.|
|**[!UICONTROL Link type]**|<ul><li>Web URL: Web URLs direct users to online content. Upon clicking, they prompt the device's default web browser to open and navigate to the designated URL.</li><li>Deeplink: Deep links are URLs guiding users to specific sections within an app even if the app is closed. When clicked, a dialog can appear, allowing users to choose from various apps capable of handling the link.</li><li> Open App: Open App URLs allow you to directly connect to content within an application. It enables your application to establish itself as the default handler for a specific type of link, bypassing the disambiguation dialog.</li></ul>|

### HTTPv1 additional options {#additional-options}

|Parameter | Description |
|---------|---------|
|**[!UICONTROL Ticker]**|Set the ticker text of your notification. Only available for devices set to Android 5.0 Lollipop.|
|**[!UICONTROL Sticky]**|When activated, the notification remains visible even after the user clicks on it. <br>If deactivated, the notification is automatically dismissed when the user interacts with it. The sticky behavior allows important notifications to persist on the screen for longer periods.|
|**[!UICONTROL Image]**|Set the image's URL to be displayed in your notification.|
|**[!UICONTROL Notification Priority]**| Set the priority level of your notification, which can be default, minimum, low, or high. The priority level determines the importance and urgency of the notification, influencing how it is displayed and whether it can bypass certain system settings. For more on this, refer to [FCM documentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
|**[!UICONTROL Notification Count]**|Set the number of new unread information to be displayed directly on the application icon. This allows the user to quickly see the number of pending notifications. |
| **[!UICONTROL Visibility]**| Set the visibility level of your notification, which can be public, private, or secret. The visibility level determines how much of the notification's content is shown on the lock screen and other sensitive areas. For more information, refer to the [FCM documentation](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility).|
|**[!UICONTROL Application variables]**|  Allow you to define notification behavior. These variables are fully customizable and are included as part of the message payload sent to the mobile device.|
