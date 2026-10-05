---
product: campaign
title: Delivery outline
description: Learn more about the Delivery outline workflow activity
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
TQID: 'https://experienceleague.adobe.com/-uyRqPAXzP-l05tmEfq4ZcJizCiGpTfY0qu-6tQ8cU0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
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
# Delivery outline{#delivery-outline}

The **delivery outline** lets you use an outline in a campaign workflow. The outline must have been created in the campaign beforehand.

To configure the activity, you simply have to select the outline you like as well as the planned contact date. You can add filtering rules by adding typologies or typology rules.

## Example: Inserting an offer via a delivery outline {#example--inserting-an-offer-via-a-delivery-outline}

The **delivery outline** activity, available in the campaign workflows, lets you present offers that are referenced in a delivery outline from the current campaign in progress.

>[!NOTE]
>
>The **Interaction** package must be installed.

1. In a workflow, add a delivery outline activity before adding a delivery activity.
1. In the delivery outline activity, specify the outline you would like to use.
1. Complete the available fields according to your delivery.
1. There are two possible cases:

    * If you would like to call the offer engine, check the **[!UICONTROL Restrict the number of propositions selected]** box. Specify the offer space and the number of propositions that will be presented in the delivery.

      The offer weights and eligibility rules will be taken into account by the offer engine.
    
    * If you do not check the box, all the offers in the delivery outline will be presented without making a call to the offer engine.

   The preview takes into account the number of offers specified in the delivery. When executing a workflow, it is the number specified in the delivery outline that is taken into account.

   ![](assets/int_compo_offre_wf1.png)
