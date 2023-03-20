---
title: Add personalization fields
description: Learn how to insert personalization data in your message content
feature: Personalization
role: User
level: Beginner
---

# Add personalization fields{#personalization-fields}

Use personalization fields to deliver personalized content on a one-to-one basis, based on the rules you set for each recipient.

A personalization field is a single data field reference used when personalizing a delivery for a specific recipient. The actual data value is inserted during the delivery analysis phase.

![message personalization sample](assets/perso-name-sample.png)

## Syntax

A personalization tag always uses the following syntax: `<%=table.field%>`.

For example, to insert the name of the recipient, stored in the recipient table, the personalization field uses the `<%= recipient.lastName %>` syntax.

>[!CAUTION]
>
>Personalization fields content cannot exceed 1024 characters.

## Insert a personalization field {#insert-a-personalization-field}

To insert personalization fields, click the drop-down icon that is accessible from any header, subject, or message body field.

![insert a personalization field](assets/perso-field-insert.png)

The personalization fields are inserted, and ready to be interpreted by Adobe Campaign: during message preparation, the fields are replaced by their value for a given recipient. 

![personalization fields in an email](assets/perso-fields-in-msg.png)

This replacement can then be tested in the **[!UICONTROL Preview]** tab. 

<!--Learn more about message preview in [this page]().-->

## Use case: personalize email subject {#personalization-fields-uc}

In the use case below, learn how to personalize an email subject and body with recipient data:

1. Create a new delivery or open an existing email delivery.
1. Browse to the **[!UICONTROL Subject]** link to edit the subject of the message.
1. Enter " **Special offer for** " and use the button in the toolbar to insert a personalization field. Select **[!UICONTROL Recipients>Title]**.
1. Repeat the operation to insert the name of the recipient. Insert spaces between all the personalization fields.
1. Click **[!UICONTROL OK]** to validate.
1. Insert the personalization in the message body. To do this, click in the message content and click the field insertion button.
1. Select **[!UICONTROL Recipient>Other...]**.
1. Select the field with the information to display and click **[!UICONTROL OK]**.
1. Click the **[!UICONTROL Preview]** tab to view the personalization result. You must select a recipient to display that recipient's message.



## Tutorial video {#personalization-field-video}

Learn how to add a personalization field to the subject line and the content of an email delivery in the following video.

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)

