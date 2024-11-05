---
title: Send emails with Adobe Campaign
description: Get started with emails in Adobe Campaign. Send personalized emails to a target population.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
---
# Design and send emails

Email deliveries let you send personalized emails to the target population. [Learn more](../send/send.md)

Learn key steps to create and configure a delivery in [this page](../start/create-message.md).

## Create your first email delivery

Create personalized and contextually relevant emails that are consistent with the rest of the customer experience.

![](assets/new-email-content.png)


In the following sample, you will learn steps to design an email delivery in Adobe Campaign which contains personalized data, links to an external URL, and a link to the mirror page.

1. **Create the delivery**

   To create a new delivery, browse to the **Campaigns** tab, click **Deliveries** and click the **Create** button above the list of existing deliveries.
   
   ![](assets/delivery_step_1.png)

1. **Select the template**

   Select a delivery template, then name your delivery. This name will only be visible to users of the Adobe Campaign console and not by your recipients, however this heading will be displayed in your list of deliveries. Click **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Import your content**

   Click the **Source** tab to paste your HTML content.
   
   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >To avoid performance issues, images included in emails cannot exceed 100 KB.

1. **Personalize your message**

   * Add the first and last names of your recipients

      To insert the first and last names of the targeted profiles in the content of the message, place the cursor where you want to insert them, and click the last icon in the toolbar, then click **[!UICONTROL Include]** and select **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Browse to the preview tab to check personalization by selecting a recipient.
   
      ![](assets/perso-check.png)

      Learn more about personalization options in [this section](personalize.md).

   * Insert a tracked link

      To take delivery recipients to an external address via an image or a text, select it and click the **[!UICONTROL Add a link]** icon in the toolbar.

      Enter the URL for the link in the **URL** field using the following format **https://www.myURL.com**, then confirm.

      ![](assets/add-a-link.png)

   * Add a mirror page

      To allow your recipients to view your delivery content in a web browser, add a link to the [mirror page](mirror-page.md) of your message.

      Place the cursor where you want to insert this link, and click the last icon in the toolbar, then click **[!UICONTROL Include]** and select **[!UICONTROL link to mirror page]**.
      
      Learn more about managing the mirror page in [this section](mirror-page.md#link-to-mirror-page).

1. You can define additional parameters for your email such as sending a copy of your messages to a BBC address, changing the message format, setting a specific encoding, etc. Learn more in [this section](email-parameters.md).

1. Once the content is ready, click **Save**: it will now be displayed in your list of deliveries, in the **[!UICONTROL Campaigns > Deliveries]** tab.

Your first email delivery is ready. You now need to define the audience, validate the delivery and send it.

Learn how to import an email content in this [use case](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html){target="_blank"}.

Learn more in the following sections:

<!--[Design an email in Campaign]-->
* [Create and use an email template](../send/create-templates.md)
* [Select the audience of your email](../audiences/gs-audiences.md)
* [Validate a delivery and send proofs](preview-and-proof.md)
* [Configure and send the delivery](configure-and-send.md)

## Test and validate your emails

Campaign offers several ways to test and validate your emails before sending them to your audiences. Learn how to preview and test your email content in [this section](../send/preview-and-proof.md).

You can:

* [Send proofs](preview-and-proof.md)
* [Add seed addresses](../audiences/test-profiles.md)
* [Check delivery analysis logs](delivery-analysis.md)

