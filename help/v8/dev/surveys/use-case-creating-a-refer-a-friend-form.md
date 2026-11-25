---
product: campaign
title: Create a Refer A Friend survey
description: Learn steps to create a Refer A Friend form
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: bd94c41a-813a-4ddb-a2bd-c3deab022482
TQID: 'https://experienceleague.adobe.com/n0qp8Q0p18fMbRYxAOu5Qj-0TCf8YgL5vF71F-ZGjbM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Use case: create a referral form{#use-case-creating-a-refer-a-friend-form}

>[!AVAILABILITY]
>
>Surveys are not available for [Campaign FFDA deployments](../../architecture/enterprise-deployment.md).

 

In this example, we want to offer a competition to the recipients in the database. The Web form will have a section for entering answers and another to refer a friend by entering their email address.

![Competition form with an identification area, a quiz area with random questions and an invitation area to refer a friend](assets/s_ncs_admin_survey_viral_sample_0.png)

The identification and competition blocks are created using the processes described previously.

To configure and create the referral block, apply the following steps:

1. Create a competition Web form with questions and a field for entering a friend's contact information as shown below:

   ![Competition form structure with an Identification, a Game and a Referral section with friend contact fields](assets/s_ncs_admin_survey_viral_sample_2.png)

   The **Your message** field lets you enter a message for the referee. The referrer must also enter their **Last name**, **First name** and **Email**.

   The information entered in the fields is stored in a specific table known as the visitor table.

   >[!NOTE]
   >
   >As long as the recipient hasn't given their consent, you cannot store them with the recipients in the database. They will be stored temporarily in the **visitor** table (**nms:visitor**) designed for viral marketing campaigns. This table is purged on a regular basis thanks to **cleansing** operations.
   >
   >In this example, we want to target recipients to suggest they take part in the competition recommended by their referrer. However in this message we also want to offer them a subscription to one of our information services. If they subscribe, they can be stored in the database.

   ![Form structure with the His last name field in the Refer a friend section selected](assets/s_ncs_admin_survey_viral_sample_5.png)

   The content of the fields which concern the referee will be used in the profile creation script and in the message sent to them.

1. Start by creating a script to link the referrer to the referee.

   It contains the following instructions:

   ![Form diagram with the Referee information script box open, setting the visitor id, forward URL and referrer fields](assets/s_ncs_admin_survey_viral_sample_4.png)

   ```javascript
   ctx.recipient.visitor.@id = xtk.session.GetNewIds(1)
   ctx.recipient.visitor.@forwardUrl = "APP5"
   ctx.recipient.visitor.@referrerEmail = ctx.recipient.@email
   ctx.recipient.visitor.@referrerFirstName = ctx.recipient.@firstName
   ctx.recipient.visitor.@referrerLastName = ctx.recipient.@lastName
   ```

   The last name, first name and email address entered in the page identification block are identified as the last name, first name and email address of the referrer. These fields will be re-injected into the body of the message sent to the referee.

   The APP5 value matches the internal name of the Web form: this information lets you find out the referee's origin, i.e. link the visitor to the Web form based on which they were created.

1. The storage box lets you gather information and store it in the database.

   ![Storage box dialog with the Visitor element selected in the reconciliation options to store the referee](assets/s_ncs_admin_survey_viral_sample_4b.png)

1. Then create the delivery template linked to the information service created during step 1. It will be selected in the **[!UICONTROL Choose scenario]** field of the information service.

   The delivery template used to create the referral offer message contains the following information:

   ![Invite a friend delivery template with a subject and HTML content that uses personalization fields](assets/s_ncs_admin_survey_viral_sample_7.png)

   This template has the following characteristics:

    * Select the visitor table as the target mapping.
    
      ![Select target dialog with Visitors (nms:visitor) selected as the target mapping of the delivery](assets/s_ncs_admin_survey_viral_sample_7b.png)

    * The referee's contact information as well as the information on the referrer are taken from the visitor table. It is inserted using the personalization button.
    
      ![Personalization menu in the delivery content, Visitor submenu listing Last name, First name, Email and Referrer fields](assets/s_ncs_admin_survey_viral_sample_7a.png)

    * This template contains a link to the competition form and the subscription link for the referee to subscribe to the newsletter.

      The subscription link is inserted via a personalization block. By default, it lets you subscribe profiles to the **newsletter** service. This personalization block can be changed to suit your needs, for example to subscribe the recipient to a different service.
    
    * The internal name ('referrer' here) will be used in the message delivery script as shown below.

   >[!NOTE]
   >
   >Refer to the [Campaign v8 documentation](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/create-templates.html){target="_blank"} for more information on delivery templates.

1. Create the second script for delivering the subscription messages.

   ![Script box Referee storage and message sending, with code that queues the referral email notification to the referee](assets/s_ncs_admin_survey_viral_sample_7c.png)

   ```javascript
   // Updtate visitor to have a link to the referrer recipient
   ctx.recipient.visitor.@referrerId = ctx.recipient.@id
   ctx.recipient.visitor.@xtkschema = "nms:visitor"
   ctx.recipient.visitor.@_operation = "update" 
   ctx.recipient.visitor.@_key = "@id" 
   xtk.session.Write(ctx.recipient.visitor)
   
   // Send email to friend
   nms.delivery.QueueNotification("referrer",
   <delivery>
   <targets>
     <deliveryTarget>
       <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
         <where>
           <condition expr={'@id IN ('+ ctx.recipient.visitor.@id +')' }/>
         </where>
       </targetPart>
      </deliveryTarget>
     </targets>
    </delivery>)
   ```

1. Publish the competition form and send an invitation to the recipients of the initial target. When one of them invites a friend, a delivery based on the **Referral offer** template is created.

   ![Completed quiz page with an Invite a friend section, and the Deliveries list showing that delivery in progress](assets/s_ncs_admin_survey_viral_sample_8.png)

   The referee is added to the visitor folder in the **[!UICONTROL Administration > Visitors node]**:

   ![Visitors folder listing the referee, with the visitor General tab showing name, email and referrer](assets/s_ncs_admin_survey_viral_sample_9.png)

   Their profile contains the information entered by their referrer. It is stored based on the configurations entered in the form script. If they decide to subscribe to the newsletter, they will be saved in the recipient table.
