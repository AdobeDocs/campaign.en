---
title: Define and personalize the SMS content
description: Learn how to define and personalize the content of an SMS delivery
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
---
# Define the SMS content {#sms-content}

To configure the content of your SMS delivery:

1. Enter the content of your message in the **[!UICONTROL Text content]** tab.
    
    ![](assets/sms_content.png){zoomable="yes"}

1. You can personalize your message by inserting personalization fields (for example adding the first name), or inserting predefined personalization block (for example adding the greetings). Click on the personalization button to add these:

    ![](assets/sms_perso.png){zoomable="yes"}

    For example, after clicking on **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, the SMS content is updated with the personalization field, as below:

    ![](assets/sms_perso_recipient.png){zoomable="yes"}

    Learn more about personalization in Adobe Campaign in [this section](../personalize.md).

1. You can preview you delivery content from the **[!UICONTROL Preview]** tab. To check your personalization settings, click on the **[!UICONTROL Test personalization]** drop-down list, and select a recipient.

    ![](assets/sms_preview.png){zoomable="yes"}

    You can check the preview of your SMS with the personalization:

    ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS messages are limited to a length of 160 characters if the Latin-1 (ISO-8859-1) code page is used. If the message is written in Unicode, it must not exceed 70 characters. Certain special characters can affect message length. For more information on message length, refer to [SMS character transliteration ](smpp-external-account.md#smpp-channel-settings) section.
>
>* When personalization fields or conditional content fields are present, the size of the message varies from one recipient to the other. The length of the message must be evaluated when personalization has been carried out.
>
>*When you launch the analysis, the length of messages is checked and a warning is displayed in the event of overflow.

After creating the content of your delivery, you can [select your audience](sms-audience.md).
