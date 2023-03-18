---
title: Personalize content
description: Learn how to personalize message content
feature: Personalization
role: User
level: Beginner
---
# Personalize content {#personalize-content}

To get the most out of every marketing campaign, Adobe Campaign gives you a way to deliver custom content that speaks to customers on their level. You can adapt your messages to each specific recipient by leveraging the data and information you have about them. It can be their first name, interests, where they live, what they bought, and much more.

With Adobe Campaign, display different types of content customized for each recipient using a single [email template](create-templates.md). In your transactional emails, such as purchase confirmation or cart abandonment emails, include product listings information for each individual within a single email template.

You can:

* Insert dynamic personalization fields. [Learn more](personalization-fields.md).
* Insert predefined personalization blocks. [Learn more](personalization-blocks.md).
* Create conditional content. [Learn more](conditional-content.md).
* Personalize the message format. [Learn more](defining-the-email-content.md#message-content).
* Insert personalized offers in your message content

>[!CAUTION]
>
>The following variables are internal variables that can be used for personalization but must not be modified: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Advanced settings

### Optimize personalization {#optimize-personalization}

You can optimize personalization using a dedicated option: **[!UICONTROL Prepare the personalization data with a workflow]**, available in the **[!UICONTROL Analysis]** tab of the delivery properties. 

During the delivery analysis, this option automatically creates and executes a workflow that stores all of the data linked to the target in a temporary table, including data from tables linked in FDA.

Checking this option can highly improve the delivery analysis performance when a lot of data are being processed, especially if the personalization data come from an external table through FDA. [Learn more](../connect/fda.md).

To use this option, follow the steps below:

1. Create a campaign. 
1. In the **[!UICONTROL Targeting and workflows]** tab of your campaign, add a **Query** activity to your workflow. 
1. Add an **[!UICONTROL Email delivery]** activity to the workflow and open it. 
1. Go to the **[!UICONTROL Analysis]** tab of the **[!UICONTROL Delivery properties]** and select the **[!UICONTROL Prepare the personalization data with a workflow]** option.
1. Configure the delivery and start the workflow to launch the analysis.

Once the analysis is done, the personalization data are stored in a temporary table through a temporary technical workflow that is created on the fly during the analysis.

This workflow is not visible in the Adobe Campaign interface. It is only meant to be a technical means to quickly store and handle personalization data.

Once the analysis is complete, go to the workflow **[!UICONTROL Properties]** and select the **[!UICONTROL Variables]** tab. There you can see the name of the temporary table that you may use to make an SQL call in order to display the IDs that it contains.


### Set a timeout for personalization {#timing-out-personalization}

To improve delivery protection, you can set a time-out period for the personalization phase.

In the **[!UICONTROL Delivery]** tab of the **[!UICONTROL Delivery properties]**, select a maximum value in seconds for the **[!UICONTROL Maximum personalization run time]** option.

During preview or sending, if the personalization phase exceeds the maximum time that you set in this field, the process will be aborted with an error message and the delivery will fail.

The default value is 5 seconds.

If you set this option to 0, there will be no time limit for the personalization phase.
