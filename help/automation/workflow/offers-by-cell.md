---
product: campaign
title: Offers by cell
description: Offers by cell
feature: Workflows, Targeting Activity, Interaction
role: User
version: Campaign v8, Campaign Classic v7
exl-id: e2216dfd-1ef8-4747-b716-576fd6498fa6
TQID: 'https://experienceleague.adobe.com/rcPG-VXEtEll374z7DpQTQOcZ3MXauiZwPTwByTUSEk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Offers by cell{#offers-by-cell}



The **[!UICONTROL Offers by cell]** activity lets you distribute the inbound population (from a query for example) into several segments and to specify an offer to present for each of these segments.

This activity can only be used with **Interaction**. Learn more about Offer management in [this section](../../v8/interaction/interaction.md).

To do this:

1. Add the **[!UICONTROL Offers by cell]** activity once you have specified the target population, then open it.
1. In the **[!UICONTROL General]** tab, select the offer space on which you want to present the offers.
1. In the **[!UICONTROL Cells]** tab, specify the different sub-sets using the **[!UICONTROL Add]** button:

    * Specify the subset population using the available filtering and limiting rules.
    * Next, select the offer that you want to present to the sub-set. The available offers are those that are eligible on the offer space that was selected at the previous step.
    
      ![](assets/int_offer_per_cell1.png)

1. Then configure a delivery activity that corresponds to your chosen channel. Refer to [Cross-channel deliveries](cross-channel-deliveries.md).
