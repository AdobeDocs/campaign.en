---
product: campaign
title: Get started with campaign typologies
description: Learn how to configure and implement campaign typologies
feature: Typology Rules
---
# Get started with campaign typologies{#about-campaign-typologies}

Campaign Optimization is the Adobe Campaign module which lets you control, filter and monitor the sending of deliveries. To avoid conflicts between campaigns, Adobe Campaign can test various combinations by applying specific constraint rules. This guarantees that the messages sent meet the needs and expectations of customers and company communication policies.

![](assets/do-not-localize/how-to-video.png) [Discover this feature in video](#typologies-video)

>[!NOTE]
>
>Depending on your offering, Campaign Optimization can be included or an add-on. Please check your license agreement.

## Typology rules and typologies {#typology-rules}

With Adobe Campaign you can design and apply four types of **typology rules**:

* **Filtering** rules which let you exclude part of the target based on criteria. [Learn more](filtering-rules.md).
* **Pressure** rules which let you control marketing fatigue. [Learn more](pressure-rules.md).
* **Capacity** rules which let you limit loads to guarantee optimal processing conditions. [Learn more](consistency-rules.md#controlling-capacity).
* **Control** rules which let you check the validity of messages before they are sent. [Learn more](control-rules.md).

Once they have been created, typology rules are grouped in campaign **typologies** which are referenced in deliveries. [Learn more](#apply-typologies).

A campaign typology can contain several typology rules, but a delivery can only reference one typology.

Built-in typology rules and typologies are available in the **[!UICONTROL Administration > Campaign management > Typology management]** node of Campaign Explorer.

For each typology, the **[!UICONTROL Rules]** tab lets you add, delete or view the typology rules to apply.

![](assets/campaign_opt_rules_tab.png)

## Key steps to apply typologies {#apply-typologies}

Key steps to create and apply a typology to your deliveries are listed below:

1. Create typology rules and create a typology to reference them into it.
   Detailed steps are listed in the following section:
   * [Pressure rules](pressure-rules.md)
   * [Filtering rules](filtering-rules.md)
   * [Capacity rules](consistency-rules.md)
   * [Control rules](control-rules.md)

1. Configure your delivery to use the typology you created. [Learn more](apply-rules.md#apply-a-typology-to-a-delivery).
1. Test and control the behavior through campaign simulations. [Learn more](campaign-simulations.md).

During delivery preparation, recipients are excluded when criterion is met. You can check logs to monitor exclusions.

Sample use cases on pressure typology rules are available in [this page](pressure-rules.md#use-cases-on-pressure-rules).

## Tutorial videos {#typologies-video}

### Set up fatigue management using typology rules

This video explains how to implement fatigue management in Adobe Campaign by leveraging typology rules.

>[!VIDEO](https://video.tv.adobe.com/v/25090?quality=12)

### Set up fatigue management using predefined filters

Fatigue management controls frequency and quantity of messaging to avoid over-solicitation of recipients. If you do not have the campaign optimization module in your campaign instance, you may configure a predefined filter that will filter the target population by the number of messages received
This video explains how to implement fatigue management in Adobe Campaign by using filters.

>[!VIDEO](https://video.tv.adobe.com/v/25091?quality=12)


