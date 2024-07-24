---
title: SMS delivery settings
description: Learn how to setup a SMS delivery
feature: SMS
role: User
level: Beginner, Intermediate
---

# SMS delivery settings {#sms-settings}

>[!IMPORTANT]
>
>This documentation is for Adobe Campaign v8.7.2 and later.
For older versions, please read the [Campaign Classic v7 documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

The technical settings needed for a SMS delivery are : 
- The routing : the SMPP external account
- The **[!UICONTROL SMS]** tab if needed

You can set up all of these in a delivery template in order to avoid to do the settings for each SMS delivery creation.

## Create a SMS delivery {#sms-delivery}

To create a new SMS delivery, follow the steps below : 

1. Create a new delivery, for example from the Delivery Dashboard, or in your Delivery folder in **[!UICONTROL Explorer]**. 
By default, it will be labeled "Email delivery"
1. Select the delivery template you created for your SMS sendings.
For standalone instance, learn more here [learn more here](sms-standalone-instance.md#sms-delivery-template).
For mid-sourcing infrastructure, learn more here

![](assets/sms_create.png){zoomable="yes"}

1. Rename your delivery in the **[!UICONTROL Label]** field and add information in **[!UICONTROL Delivery code]** field and **[!UICONTROL Nature]** list if needed for the tracking. You can also add a **[!UICONTROL Description]** to your delivery
1. Click on **[!UICONTROL Continue]** button.
Now, you have all the settings of your template in your delivery.
1. You can check in the **[!UICONTROL Properties]** button that all is set up as needed

![](assets/sms-settings.png){zoomable="yes"}

You can now configure your [SMS content](sms-content.md).
