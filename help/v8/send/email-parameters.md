---
title: Email parameters in Adobe Campaign
description: Learn about options and settings that are specific to email delivery in Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
---
# Email parameters {#email-parameters}

This section presents the options and parameters available from the delivery properties that are specific to email delivery.

## Use Email BCC {#email-bcc}

You can configure Adobe Campaign to keep a copy of emails sent from your platform. This option is detailed in [this page](email-bcc.md).

## Select message formats {#selecting-message-formats}

You can change the format of email messages sent. To do this, edit the delivery properties and click the **[!UICONTROL Delivery]** tab.

![](assets/email-message-format.png)

Select the format of the email in the lower section of the window:

* **[!UICONTROL Use recipient preferences]** (default mode)

  The message format is defined according to the data stored in the recipient profile and stored by default in the **[!UICONTROL email format]** field (@emailFormat). If a recipient wishes to receive messages in a certain format, this is the format sent. If the field is not filled in, a multipart-alternative message is sent (see below).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  The message contains both formats: text and HTML. The format displayed on reception depends on the configuration of the recipient's mail software (multipart-alternative).

  >[!IMPORTANT]
  >
  >This option includes both versions of the document. It therefore reduces the delivery throughput, because the message size is greater.

* **[!UICONTROL Send all messages in text format]**

  The message is sent in text format. HTML format will not be sent, but used for the mirror page only when the recipient clicks on the message.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Set character encoding {#character-encoding}

In the **[!UICONTROL SMTP]** tab of the delivery parameters, the **[!UICONTROL Character encoding]** section allows you to set a specific encoding.

The default encoding is UTF-8. If some of your recipients' email providers do not support the UTF-8 standard encoding, you may want to set a specific encoding to properly display the special characters to your emails' recipients.

For example, you want to send an email containing Japanese characters. To make sure that all characters will be correctly displayed to your recipients in Japan, you may want to use an encoding that will support the Japanese characters rather than the standard UTF-8.

To do this, select the **[!UICONTROL Force the encoding used for messages]** option in the **[!UICONTROL Character encoding]** section and choose an encoding from the drop-down list that is displayed.

![](assets/email-smtp-encoding.png)

## Manage bounce emails {#managing-bounce-emails}

The **[!UICONTROL SMTP]** tab of the delivery properties lets you also configure the management of bounce mails.

* **[!UICONTROL Errors-to-address]**: By default, bounced emails are received in the default error box of the platform, but you can define a specific error address for a delivery.

* **[!UICONTROL Bounce address]**: You can also define another address to which the unprocessed bounced emails are forwarded. This address allows to investigate the reasons for bouncing when emails could not be automatically qualified by the application.

Each of these fields can be personalized using the dedicated icon. Learn more on personalization fields in [this section](personalization-fields.md).

![](assets/email-smtp-bounce.png)

For more on bounce mail management, see [this section](delivery-failures.md#bounce-mail-management).

## Enable One-click List-unsubscribe {#one-click-list-unsubscribe}

The one-click list unsubscribe URL is an unsubscribe link or button displayed next to the email sender information, and lets recipients instantly opt out of your mailing lists with a single click. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}

This header can be used as an alternative to the "Report as SPAM" icon. It displays as an "Unsubscribe" link in the ISPs' email interfaces. Using this functionality lowers complaint rates and helps to protect your reputation. Feedback will be executed as an unsubscribe.

>[!IMPORTANT]
>
>To display the one-click unsubscribe URL in the email header, the recipients' email client must support this feature.

To enable One-click List-unsubscribe, select the **[!UICONTROL Addition of One-click List-Unsubscription Header]** option in the **[!UICONTROL SMTP]** tab of the delivery properties.

>[!NOTE]
>
>This option is enabled by default.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

Depending on the email client, clicking the unsubscribe link in the email header can have the following impacts:

* If the email client is using the "One-Click" List-Unsubscribe method, the recipient is directly opted-out.

  >[!NOTE]
  >
  >Major ISPs such as Google and Yahoo! are requiring senders to comply with **One-Click List-Unsubscribe**.

* If the email client does not support One-Click List-Unsubscribe, they can still use the "mailto" List-Unsubscribe method, which sends a pre-filled email to the unsubscribe address specified in the email header.

>[!NOTE]
>
>You can also set the [One-Click List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} and ["mailto" List-Unsubscribe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"} methods manually. The detailed steps are described in the Experience Cloud [Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}.


## Add SMTP headers {#adding-smtp-headers}

It is possible to add SMTP headers to your deliveries. To do this, use the relevant section of the **[!UICONTROL SMTP]** tab in the delivery.

The script entered in this window must reference one header per line in the following form: **name:value**.

Values are encoded automatically if necessary.

>[!IMPORTANT]
>
>Adding a script for inserting additional SMTP headers is reserved for advanced users.
>
>The syntax of this script must comply with the requirements of this content type: no unused space, no empty line, etc.

![](assets/email-smtp-headers.png)


## Generate mirror page {#generating-mirror-page}

The mirror page is an HTML page accessible online via a web browser. Its content is identical to the email. It can be useful if your recipients are experiencing rendering issues or broken images when trying to view your email in their inbox.

Learn how to insert a link to the mirror page in [this section](mirror-page.md)
