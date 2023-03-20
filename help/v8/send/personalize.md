---
title: Personalize content
description: Learn how to personalize message content
feature: Personalization
role: User
level: Beginner
---
# Personalize content {#personalize-content}

To get the most out of every marketing campaign, Adobe Campaign gives you a way to deliver custom content that speaks to customers on their level. Based on profile data, personalization capabilities  to create a custom experience for different groups and individuals: you can adapt your messages to each specific recipient by leveraging the data and information you have about them. It can be their first name, interests, where they live, what they bought, and much more.

Adobe Campaign simplifies personalization: you can display different types of content customized for each recipient using a single [email template](create-templates.md). In your transactional messages, such as purchase confirmation or cart abandonment emails, include product listings information for each individual within a single email template.


## Personalization strategies {#personalization-strategy}

Use Campaign to create dynamic content and send personalized messages. Personalization capabilities can be combined to improve your messages and create a custom user experience.

You can personalize the message content by:

* Inserting dynamic **personalization fields**

    Personalization fields are used for first-level personalization of your messages. You can select any field available in the database from the personalization editor. For a delivery, you can select any field related to the recipient, the message or the delivery. These personalization attributes can be inserted in the subject line or the body of your messages. [Learn more](personalization-fields.md).

    The following syntax inserts the city of the recipient in your content: <%= recipient.location.city %>.
    
* Inserting pre-defined **content blocks**
    
    Campaign comes with a set of personalization blocks which contain a specific rendering that you can insert into your deliveries. For example, you can add a logo, a greeting message, or a link to the mirror page of the message. Content blocks are available from a dedicated entry un the personalization editor. [Learn more](personalization-blocks.md).

* Create **conditional content**

    Configure conditional content to add dynamic personalization based on the recipient’s profile for example. Text blocks and/or images are inserted when a particular condition is true. [Learn more](conditional-content.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Guardrails and recommendations{#perso-guardrails}

### Personalization time out{#perso-timeout}

To improve delivery protection, you can set a time-out period for the personalization phase.

In the **[!UICONTROL Delivery]** tab of the **[!UICONTROL Delivery properties]**, select a maximum value in seconds for the **[!UICONTROL Maximum personalization run time]** option.

During preview or sending, if the personalization phase exceeds the maximum time that you set in this field, the process will be aborted with an error message and the delivery will fail.

The default value is 5 seconds.

If you set this option to 0, there will be no time limit for the personalization phase.


### Internal  variables{#internal-variables}

The following variables are internal variables that can be used for personalization but must not be modified: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Tutorial video {#personalization-video}

Understand the different types of dynamic content and learn how create and apply personalization blocks and conditional statements to a delivery.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)