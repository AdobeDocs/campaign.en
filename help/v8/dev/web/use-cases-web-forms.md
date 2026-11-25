---
product: campaign
title: 'Use cases: web forms'
description: 'Use cases: web forms'
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
---
# Use cases: web forms{#use-cases-web-forms}

 

## Create a subscription form with double opt-in {#create-a-subscription--form-with-double-opt-in}

When you offer information services, recipients need to subscribe to receive all linked communications. To avoid improper communications and make sure the recipient subscribed intentionally, we recommend sending a subscription confirmation request to create a double opt-in. The subscription will only be effective once the user clicks the link included in the confirmation message.

This example is based on the following scenario:

1. Creating a newsletter subscription form on a website that contains a checkbox for subscribing to a temporary service. This service will enable you to deliver subscription confirmation messages.
1. Creating the subscription confirmation delivery with a delivery template linked to the Web form. It contains the confirmation link that calls up the form for newsletter subscription and displays a subscription approval message.

### Step 1 - Creating information services {#step-1---creating-information-services}

1. Create the newsletter subscription service to be offered to your recipients. For more information on how to create a newsletter, refer to [this section](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}.

   ![Service dialog for the Weekly Newsletter service with Label, Internal name, Type Email and Mode Newsletter fields.](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. Create a second information service, a temporary service linked to a delivery template for sending subscription confirmation messages.

   ![Temporary Service (temp_service) dashboard showing Type Email, Mode Newsletter and its folder.](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### Step 2 - Creating confirmation messages {#step-2---creating-confirmation-messages}

Confirmation messages are sent via a dedicated delivery template referenced at the temporary service level.

1. In the **[!UICONTROL Explorer]** , select **[!UICONTROL Resources > Templates > Delivery templates]**.
1. Create a delivery template for sending the subscription confirmation messages. 
1. Click the **[!UICONTROL To]** button in the **[!UICONTROL Email parameters]** to associate the delivery template with the Subscriptions target mapping instead of Recipients.

   ![Select target dialog on the delivery template with the Subscriptions (nms:subscription) target mapping selected.](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. Since the recipients of this delivery haven't confirmed their approval, they are still on the database denylist. For them to receive this communication, you need to authorize deliveries based on this template to target recipients on the denylist.

   To do this, click the **[!UICONTROL Exclusions]** tab.

1. Click the **[!UICONTROL Edit...]** link and uncheck the **[!UICONTROL Exclude recipients who no longer want to be contacted]** option.

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >This option may only be disabled in this type of context.

1. Personalize your delivery and insert the confirmation link into the message content. This link lets you access the Web form to record subscription confirmation.

   ![Confirmation email in the delivery editor with a first name personalization field and a Click here link.](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. With the DCE, link your URL to the Web form. Since the Web form is not yet created, replace the value as soon as you create it.

   ![Hypertext link pane with the Web application field, still empty, for the Click here link in the confirmation email.](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. Finally, link this template to the temporary service previously created.

   ![Temporary Service Edit tab with the confirmation delivery selected in the Subscription field.](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### Step 3 - Creating the subscription form {#step-3---creating-the-subscription-form}

The Web form enables both recipient subscription and subscription confirmation.

The Web form workflow will include the following activities:

![Web form workflow: Preloading, Test, then Email empty leads to Script Blocklist, Subscription, Storage, End.](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

To do this, follow the steps below:

1. Create a Web form and choose the template **[!UICONTROL Newsletter subscription (subNewsletter)]**.

   ![New Web application dialog with the Newsletter subscription (subNewsletter) template selected.](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. In the **[!UICONTROL Edit]** tab, we need to configure the existing workflow since we want to add a confirmation message to the recipients who want to subscribe.

   To do so, double-click the **[!UICONTROL Preloading]** box and configure it as follows. 

   ![Preloading activity dialog with Auto-load data referenced in the form and Skip preloading if no ID selected.](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   This means that if the user accesses this form via the link in the confirmation message, their profile information will be loaded. If they access the Web form via a page of the website, no information will be loaded.

1. Add a **[!UICONTROL Test]** activity to your workflow.

   ![Web form workflow with a Test activity that branches on Email empty to Subscription, Storage and End.](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   The **[!UICONTROL Test]** activity can concern the recipient email. In this case, configure it as follows:

   ![Test activity branch editor with the condition @email is not empty.](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. Add two **[!UICONTROL Script]** activities to your workflow.

   ![Web form workflow with a Script activity on each branch of the Test activity.](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   The first **[!UICONTROL Script]** activity will add recipients on denylist until they have confirmed their subscription to the newsletter. Its content must be as follows:

   ```javascript
   ctx.recipient.@blackList=1
   ```

   ![Script Blocklist activity containing the script ctx.recipient.@blackList=1.](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)

   The second **[!UICONTROL Script]** activity authorizes deliveries to be sent to the users and subscribes them to the newsletter. The last two lines of the script will allow you to transfer your recipients from the temp folder to another folder and be reconciled with existing profiles as soon as they have confirmed the subscription.

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   
   ```

   >[!NOTE]
   >
   >The **[!UICONTROL Temp]** partition can also be purged on a regular basis using a workflow.

   ![Second Script activity containing the unblocklist, Subscribe, folder and Unsubscribe script lines.](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. Double-click the **[!UICONTROL Subscription]** activity to personalize the subscription form and link a checkbox with the temporary service previously created.

   ![Page editor with the consent checkbox linked to the Temporary Service in the Service field.](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. Configure the **[!UICONTROL Storage]** activity to save the information entered in the form page.

   This activity lets you create recipient profiles in a dedicated temporary folder to set them apart from the profiles in the database, whom communications can be sent to.

   ![Storage activity dialog with the Temp folder set as the creation folder.](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >You must not define any reconciliation options.

1. Add two **[!UICONTROL End]** activities to display a message for the user.

   The second **[!UICONTROL End]** box will display the confirmation message once the subscription is complete.

   ![End activity dialog with the message Your subscription is complete. You will soon receive our Newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. Once the Web form is created and configured, you can now reference it in the delivery template to send confirmation messages.

   ![Confirmation delivery with the Click here link pointing to the Newsletter subscription double opt-in Web application.](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### Step 4 - Publishing and testing the form {#step-4---publishing-and-testing-the-form}

You can now publish the form to make it accessible to users.

![Web application dashboard with the Publish button and the message that it must be published to be accessed online.](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

Subscription to the newsletter involves the following steps:

1. The user of the website logs on to the subscription page and approves the form.

   ![Newsletter subscription form in a browser with name and email filled in, consent box checked and I subscribe button.](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   They are notified via a message in their browser that their request has been taken into account.

   ![Browser End page saying the request has been registered and a message will follow.](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   The user is added to the Adobe Campaign database in the **[!UICONTROL Temp]** folder, and their profile is on denylist until they confirm their subscription with the email.

   ![Temp recipients folder with the new profile selected and No longer contact (by any channel) checked.](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. A confirmation message including a link for approving their subscription is sent to them.

   ![Subscription confirmation email with a Click here link to confirm the newsletter subscription.](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. When they click this link, the approval page is displayed in their browser.

   ![Browser page titled Congratulations! confirming the subscription is now active.](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   In Adobe Campaign, the user profile is updated:

    * they are no longer on denylist,
    * they are subscribed to the information service.
    
      ![Updated recipient profile with No longer contact cleared and the Newsletter Movie subscription listed.](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## Displaying different options depending on the selected values {#displaying-different-options-depending-on-the-selected-values}

In the following example, the user is asked to select a type of vehicle. You can display the available vehicle categories according to the type selected. This means that the items displayed in the right-hand column depend on the user's selection:

![Car selection page with a Type of car drop-down list set to Select.](assets/s_ncs_admin_survey_condition_sample0.png)

* When the user selects 'private vehicle', the choice between "Compact" and "Minivan" is offered.

  ![Car selection page with Personal car selected, showing the Standard and Compact options.](assets/s_ncs_admin_survey_condition_sample2.png)

* When the user selects 'commercial vehicle', a selection is displayed in a drop-down list: 

  ![Car selection page with Moving truck selected and a Class drop-down list of vehicle types.](assets/s_ncs_admin_survey_condition_sample1.png)

In this example, the vehicle type is not stored in the database. The drop-down list is configured as follows: 

![Type of car combo box properties with the values Select, Personal car and Moving truck.](assets/s_ncs_admin_survey_condition_config1.png)

This information is stored in a local variable.

The right-hand column's conditional display is configured in the containers: 

![Storage dialog with the Variable option selected for the Type of car field.](assets/s_ncs_admin_survey_condition_config1bis.png)

* Conditional visibility of fields for a private vehicle:

  ![Visibility condition on the Personal Car container: type of car equal to Personal car.](assets/s_ncs_admin_survey_condition_config2.png)

* Conditional visibility of fields for a commercial vehicle:

  ![Visibility condition on the Truck/Van container: type of car equal to Moving truck.](assets/s_ncs_admin_survey_condition_config3.png)
