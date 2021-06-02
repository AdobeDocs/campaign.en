---
product: Adobe Campaign
title: Send emails with Adobe Campaign
description: Get started with emails in Campaign
feature: Overview
role: Data Engineer
level: Beginner
---
# Design and send emails

Email deliveries let you send personalized emails to the target population. 

[!DNL :arrow_upper_right:] Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Create your first email delivery

Create personalized and contextually relevant emails that are consistent with the rest of the customer experience.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Learn how to create an email delivery in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


In the following sample, you will learn steps to design an email delivery in Adobe Campaign which contains personalized data, links to an external URL, a link to the mirror page and a link to a web form.

1. Create the delivery

   To create a new delivery, browse to the **Campaigns** tab, click **Deliveries** and click the **Create** button above the list of existing deliveries.
   
   ![](assets/delivery_step_1.png)

1. Select the template

   Select a delivery template, then name your delivery. This name will only be visible to users of the Adobe Campaign console and not by your recipients, however this heading will be displayed in your list of deliveries. Click **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. Import your content

   Click the **Source** tab to paste your HTML content.
   
   ![](assets/paste-content.png)


1. Personalize your message


   * Display the first and second names of your recipients

      To insert the first and second names of your recipients into a text field in your delivery, click your chosen text field, then place your cursor where you want to display them. Click the first icon in the pop-up toolbar, then click **[!UICONTROL Personalization block]**. Select **[!UICONTROL Greetings]**, then click **[!UICONTROL OK]**.

   * Insert a link into an image

      To take delivery recipients to an external address via an image, click on the relevant image to display the pop-up toolbar, place the cursor on the first icon then click **[!UICONTROL Link to an external URL]**.

      Enter the URL for the link in the **URL** field using the following format **https://www.myURL.com**, then confirm.

      The link can be changed at any time using the section to the right of the window.

   * Insert a link into text

      To integrate an external link into the text in your delivery, select some text or a block of text then click on the first icon in the pop-up toolbar. Click **[!UICONTROL Link to an external URL]**, enter the link address into the **[!UICONTROL URL]** field.

      The link can be changed at any time using the section to the right of the window.

   * Add a mirror page

      To allow your recipients to view your delivery content in a Web browser, you can integrate a link to a mirror page into your delivery.

      Click the text field in which you wish to see the link posted. Click the first icon in the pop-up toolbar, select **[!UICONTROL Personalization block]**, then **[!UICONTROL Link to Mirror Page (MirrorPage)]**. Click **[!UICONTROL Save]** to confirm.

   * Integrate a link to a Web application

      The Digital Content Editor lets you integrate links to Web applications from your Adobe Campaign console, such as a landing page or a form page. For more on this, refer to [Link to a Web application](../../web/using/editing-content.md#link-to-a-web-application).

      Select a text field for your link to a Web application, then click the first icon. Choose **[!UICONTROL Link to a Web application]**, then select the desired application by clicking the icon at the end of the **Web Application** field.

1. Send messages

   Once the content is integrated, save the delivery by clicking **Save**. It will now be displayed in your list of deliveries, found in the **[!UICONTROL Campaigns > Deliveries]** tab.


## Create content and select the audience

You can create directly into Campaign or import your audience, as well as your email content. Use the links below to learn how to:

* Design an email in Campaign
   [!DNL :arrow_upper_right:] [Learn how to design an email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* Import an email content
   [!DNL :arrow_upper_right:] [Use case: Create a workflow to load a delivery content](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Create and use an email template
   [!DNL :arrow_upper_right:] [Learn more about email templates](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* Select the audience of your email
   [!DNL :arrow_upper_right:] [Learn how to define the target population](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Validate a delivery and send proofs
   [!DNL :arrow_upper_right:] [Learn key steps to validate a delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Add [seed addresses](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Test and validate your emails

Campaign offers several ways to test and validate your emails before sending them to your audiences.

[!DNL :arrow_upper_right:] [Apply best practices listed in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

You can:

* Check delivery analysis logs
* Send proofs
* Add seed addresses
* Use control groups
* Check email rendering

[!DNL :arrow_upper_right:] [Learn more in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Monitor your emails

Once sent, check your delivery status in the Delivery Dashboard and access delivery logs and reports confirm messages were correctly sent.

[!DNL :arrow_upper_right:] [Learn more in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

