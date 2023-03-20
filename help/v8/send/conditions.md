---
title: Conditional content
description: Learn how to create conditional content 
feature: Personalization
role: User
level: Beginner
---

# Create conditional content{#conditional-content}

By configuring conditional content fields, you can create advanced personalization. Complete text blocks and/or images are replaced when a particular condition is satisfied.


## Use conditions in an email {#conditions-in-an-email}

In the example below, learn how to create a message, dynamically personalized on the recipient's city and interests.

* Change the message depending on the recipient's city,
* Personalize the content of the offer according to the recipient's interests.

To create conditional content according to the value of a field, apply the following steps:

1. Open an existing delivery or create a new email delivery.
1. In the email content editor, click the personalization icon and select **[!UICONTROL Conditional content > If]**.

   ![Insert a condition](assets/condition-insert.png)

    The personalization elements are inserted in the message body. You must now configure them.

1. Fill in the parameters of the **if** expression.

    * Select the first element of the expression, **`<FIELD>`**, and click the personalization icon to replace it with the test field.
    * Replace **`<VALUE>`** with the value of the field for which the condition will be satisfied. This value must be in quotation marks.
    * Specify the content to be inserted when the condition is satisfied. This can be a text, an image, a form, a hypertext link, etc.

    ![Condition in an email](assets/condition-in-email.png)

1. Click the **[!UICONTROL Preview]** tab to view the content of the message according to the delivery recipient. Select a recipient for which the condition is true to check the content. Then select another recipient for which it is false and check again.

You can add other cases and define different content according to the values of one or more fields. To do this, use **[!UICONTROL Conditional content > Else]** and **[!UICONTROL Conditional content > Else if]**. These expressions are configured in the same way as the **if** expression.

>[!CAUTION]
>
>The **%> <%** characters must be deleted after adding **Else** and **Else if** conditions.


## Use case: create a multilingual email {#creating-multilingual-email}

In the example below, learn how to create a multilingual email. Content displays in one language or the other depending on the recipient's preferred language.

1. Create an email and select the target population. In this example, the condition to display one version or the other will be based on the **Language** value of the recipient's profile. These values are set to **EN**, **FR**, **ES**.
1. In the email HTML content, click the **[!UICONTROL Source]** tab and paste the following code:

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. Test email content in the **[!UICONTROL Preview]** tab by selecting recipients with different preferred languages.

   >[!NOTE]
   >
   >As no alternative version has been defined in the email content, make sure to filter target population before sending the email.

## Tutorial video {#conditionnal-content-video}

Learn how to add conditional content to a delivery on the example of a multilingual newsletter.

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)

