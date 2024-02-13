---
title: Work with Campaign and Adobe Experience Manager
description: Learn how to work with Campaign and Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
---
# Work with Campaign and Adobe Experience Manager {#ac-aem}

Integration between Adobe Campaign and Adobe Experience Manager allows you to manage the content of your email deliveries as well as your forms directly in Adobe Experience Manager. You have the option to either import your **Adobe Experience Manager** content into Campaign or connect your **Adobe Experience Manager as a Cloud service** account, allowing you to edit your content directly within the Web interface.

![](../assets/do-not-localize/book.png) [Discover how to edit your AEM content within Campaign Web Interface](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/content/design-content/aem-assets.html?lang=en)

![](../assets/do-not-localize/book.png) [Learn more about Adobe Experience Manager in this document](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html#aem-and-adobe-campaign-integration-workflow)

## Authoring with Adobe Experience Manager {#integrating-with-aem-assets}

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Experience Manager with Campaign.

This integration can be used for example to create a newsletter in Adobe Experience Manager which will then be used in Adobe Campaign as part of an email campaign.

**From Adobe Experience Manager:**

1. Navigate to your [!DNL Adobe Experience Manager] author instance and click Adobe Experience at the upper left corner of the page. Choose **[!UICONTROL Sites]** from the menu.

   ![](assets/aem_authoring_1.png)

1. Access **[!UICONTROL Campaigns > Name of your brand (here we.Shopping) > Main Area > Email]**.

1. Click **[!UICONTROL Create]** and select **[!UICONTROL Page]** from the dropdown menu.

   ![](assets/aem_authoring_2.png)

1. Select the **[!UICONTROL Adobe Campaign Email]** template and name your newsletter.

1. After creating your page, access the **[!UICONTROL Page information]** menu and click **[!UICONTROL Open Properties]**.

   ![](assets/aem_authoring_3.png)

1. Customize your email content by adding components, such as personalization fields from Adobe Campaign.. [Learn more](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=en#editing-email-content)

1. Once your email is ready, navigate to the **[!UICONTROL Page information]** menu and click **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_4.png)

1. From the first drop-down, select **[!UICONTROL Approve Adobe Campaign]** as workflow model and click **[!UICONTROL Start workflow]**.

   ![](assets/aem_authoring_5.png)

1. A disclaimer will appear at the top of your page stating, `This page is subject to the workflow Approve for Adobe Campaign`. Click **[!UICONTROL Complete]** next to the disclaimer to confirm the review and click **[!UICONTROL Ok]**.

1. Click **[!UICONTROL Complete]** again and select **[!UICONTROL Newsletter approval]** in the **[!UICONTROL Next Step]** drop-down.

   ![](assets/aem_authoring_6.png)

Your newsletter is now ready and synchronized in Adobe Campaign.

**From Adobe Campaign:**

1. From the **[!UICONTROL Campaigns]** tab, click **[!UICONTROL Deliveries]** then **[!UICONTROL Create]**.

1. Choose the **[!UICONTROL Email delivery with AEM content (mailAEMContent)]** template from the **[!UICONTROL Delivery template]** drop-down menu.

   ![](assets/aem_authoring_7.png)

1. Add a **[!UICONTROL Label]** to your delivery and click **[!UICONTROL Continue]**.

1. Click **[!UICONTROL Synchronize]** to access your AEM deliveries.

   If the button is not visible in your interface, navigate to the **[!UICONTROL Properties]** button and access the **[!UICONTROL Advanced]** tab. Ensure that the **[!UICONTROL Content editing mode]** field is configured to **[!UICONTROL AEM]**, and input your AEM instance details in the **[!UICONTROL AEM account]** field.

   ![](assets/aem_authoring_8.png)

1. Select the AEM delivery previously created in [!DNL Adobe Experience Manager] and confirm by clicking **[!UICONTROL Ok]**.

1. You can directly insert assets from your [!DNL Adobe Experience Manager Assets] or [!DNL Adobe Experience Manager Assets Library] while editing an email in Adobe Campaign. [Learn more](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/overview.html).

   To use your **Adobe Experience Manager Assets library**, access the **[!UICONTROL Properties]** of your AEM delivery and select the **[!UICONTROL Advanced]** tab. Enable the **[!UICONTROL Use above AEM instance as shared asset library]** option.

   ![](assets/aem_authoring_9.png)

1. Ensure to click the **[!UICONTROL Refresh content]** button whenever modifications are made to your AEM delivery.

Your email is now ready to be send to your audience.
