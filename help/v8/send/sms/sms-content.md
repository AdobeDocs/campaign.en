---
title: SMS define the content
description: Learn how to setup the content of an SMS delivery
feature: SMS
role: User
level: Beginner, Intermediate
---

# SMS content {#sms-content}

To configure the content of your SMS delivery:

1. Enter the content of your message in the **[!UICONTROL Text content]** wizard
    
    ![](assets/sms_content.png){zoomable="yes"}

1. You can personalize your message by inserting personalization fields (for example adding the first name), or inserting predefined personalization block (for example adding the greetings). You can click on the personalization button to add these:

    ![](assets/sms_perso.png){zoomable="yes"}

    After clicking on **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, you will have the personalization like this:

    ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. You can preview you delivery by going in the **[!UICONTROL Preview]** tab and by clicking on **[!UICONTROL Test personalization]** drop-down list, and by choosing a recipient in the **[!UICONTROL Recipient]** table.

    ![](assets/sms_preview.png){zoomable="yes"}

    You will have the preview of your SMS with the personalization:

    ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* SMS messages are limited to a length of 160 characters if the Latin-1 (ISO-8859-1) code page is used. If the message is written in Unicode, it must not exceed 70 characters. Certain special characters can affect message length. For more information on message length, refer to [SMS character transliteration ](smpp-external-account.md#smpp-channel-settings) section.
>
>* When personalization fields or conditional content fields are present, the size of the message varies from one recipient to the other. The length of the message must be evaluated when personalization has been carried out.
>
>*When you launch the analysis, the length of messages is checked and a warning is displayed in the event of overflow.

After creating the content of your delivery, you can [select your audience](sms-audience.md).