---
title: Personalization fields
description: Learn how to insert personalization data in your message content
feature: Personalization
role: User
level: Beginner
---

# Personalization fields{#personalization-fields}

Use personalization fields to deliver personalized content on a one-to-one basis, based on the rules you set for each recipient.

A personalization field is a single data field reference used when personalizing a delivery for a specific recipient. The actual data value is inserted during the delivery analysis phase.

## Data sources {#data-sources}

Personalization fields can come from two types of data source, according to the delivery mode selected:

* Adobe Campaign database data source. 
    This is the most common case, with for example 'recipient personalization fields'. These are all the fields defined in the recipients table, whether standard fields (typically: last name, first name, address, city, date of birth, etc.) or user defined fields.
* External data source. 
    These are all the fields defined in the columns of the file presented as input during a delivery using the data found in an external file.


## Syntax

A personalization tag always uses the following syntax: **<%=table.field%>**.

For example, the personalization field with the **<%= recipient.LastName %>** syntax is used to insert the name of the recipient, stored in the recipient table.

>[!CAUTION]
>
>Personalization fields content cannot exceed 1024 characters.

## Insert a personalization field {#insert-a-personalization-field}

To insert personalization fields, click the drop-down icon that is accessible from any header, subject, or message body editing field.

![](assets/s_ncs_user_add_custom_field.png)

After the selection of a data source (recipient fields or file field), this insertion takes the form of a command that will be interpreted by Adobe Campaign and replaced by the value of the field for a given recipient. The physical replacement can then be viewed in the **[!UICONTROL Preview]** tab.

## Personalization fields example {#personalization-fields-example}

We create an email in which we will first insert the name of the recipient and then add the profile creation date in the body of the message. To do this:

1. Create a new delivery or open an existing email type delivery.
1. In the delivery wizard, click **[!UICONTROL Subject]** to edit the subject of the message and enter a subject.
1. Enter " **[!UICONTROL Special offer for]** " and use the button in the toolbar to insert a personalization field. Select **[!UICONTROL Recipients>Title]**.

    ![](assets/s_ncs_user_insert_custom_field.png)

1. Repeat the operation to insert the name of the recipient. Insert spaces between all the personalization fields.
1. Click **[!UICONTROL OK]** to validate.
1. Insert the personalization in the message body. To do this, click in the message content and click the field insertion button.
1. Select **[!UICONTROL Recipient>Other...]**.

   ![](assets/s_ncs_user_insert_custom_field_b.png)

1. Select the field with the information to display and click **[!UICONTROL OK]**.

   ![](assets/s_ncs_user_insert_custom_field_c.png)

1. Click the **[!UICONTROL Preview]** tab to view the personalization result. You must select a recipient to display that recipient's message.

   ![](assets/s_ncs_user_insert_custom_field_d.png)

   >[!NOTE]
   >
   >When a delivery is part of a workflow, you can use the data from the temporary workflow table. This data is grouped in the **[!UICONTROL Target extension]** menu. For more on this, refer to [this section](../../workflow/using/data-life-cycle.md#target-data).
