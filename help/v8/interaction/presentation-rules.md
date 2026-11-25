---
product: campaign
title: Presentation rules
description: Presentation rules
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Presentation rules{#presentation-rules}

 

## Creating a presentation rule {#creating-a-presentation-rule}

In our database, there are several travel offers for Europe, Africa, the United States and Canada. We want to send offers for a trip to Canada, but if the recipient refuses this type of offer, we don't want to send it to them again.

We are going to configure our rule so that the trip to Canada is only offered once per recipient and not offered again if rejected.

1. In the Adobe Campaign tree, go to the **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]** node.
1. Create a new **[!UICONTROL Offer presentation]** type rule.

   ![Typology rule creation form with the Rule type list open and Offer presentation selected](assets/offer_typology_example_001.png)

1. Change its label and its description if necessary.

   ![Typology rule General tab with a label, the Offer presentation type, Email channel and a description entered](assets/offer_typology_example_002.png)

1. Choose the **[!UICONTROL All channels]** option to extend the rule to all channels. 

   ![Channel list of the typology rule with All channels selected](assets/offer_typology_example_003.png)

1. Click the **[!UICONTROL Edit expression]** link and choose the **[!UICONTROL Category]** node as an expression.

   ![Query window with the Select an expression dialog opened to choose the Category field](assets/offer_typology_example_004.png)

1. Choose the category that matches your travel offer for Canada and click **[!UICONTROL OK]** to close the query window.

   ![Query on Category equal to Canada, with the Canada folder selected in the Travel offer category tree](assets/offer_typology_example_005.png)

1. In the **[!UICONTROL Offer presentation]** tab, choose the same dimensions as those configured in the environment. 

   ![Offer presentation tab showing the Targeting dimension and Storage dimension, which match the environment](assets/offer_typology_example_006.png)

1. Specify the period during which the rule will apply.

   ![Offer presentation tab with the Sliding period, Period considered field set to 10d](assets/offer_typology_example_007.png)

1. Limit the proposition to one so that recipients that have already rejected a trip to Canada will not receive another similar offer. 

   ![Offer presentation tab with the Maximum number of propositions Quantity field set to 1](assets/offer_typology_example_008.png)

1. Select the **[!UICONTROL Offers for the same category]** filter to exclude all offers from the **Canada** category.

   ![Offers drop-down in Propositions to count with Offers for the same category selected](assets/offer_typology_example_020.png)

1. Select the **[!UICONTROL Rejected propositions]** filter to take into account only propositions rejected by the recipient. 

   ![Proposition status drop-down in Propositions to count with Rejected propositions selected](assets/offer_typology_example_021.png)

1. Choose the recipients for which this rule will apply.

   In our example, we will choose the **Frequent travelers** recipients.

   ![Edit filtering query wizard selecting the Frequent travellers recipient folder as the rule target](assets/offer_typology_example_009.png)

1. Reference the rule in an offer typology.

   ![Typologies tab of the rule with the Add typologies dialog listing the Offers typology selected](assets/offer_typology_example_013.png)

1. Go to the offer environment, (**Environment - Recipient** in this case) and reference the new typology just created using the drop-down list in the **[!UICONTROL Eligibility]** tab.

   ![Eligibility tab of the offer environment with the Offer presentation typology list showing Offers](assets/offer_typology_example_014.png)

## Applying the presentation rule {#applying-the-presentation-rule}

Here is an application example of the previously created typology rule.

We want to send a first offer proposition belonging to the Canada category. If the offer is rejected once by any of the recipients, it will not be offered to them again.

1. In the **Frequent travelers** recipient folder, choose one of the profiles to check the offers for which they are eligible: click the **[!UICONTROL Propositions]** tab, then the **[!UICONTROL Preview]** tab.

   In our example, **Tim Ramsey** is eligible for an offer which is part of the **Americas** category.

   ![Recipient Propositions tab, Preview sub-tab, listing the eligible offer for the Americas category](assets/offer_typology_example_015.png)

1. Start by creating an email delivery which will target your **Frequent travelers** recipients with offers.
1. Select the offer engine call-up parameters.

   In our example, the **Travel in America** category is chosen, which contains the **Canada** and **United States** sub-categories.

   ![Offer management dialog of an email delivery with the Americas category and 2 propositions per message](assets/offer_typology_example_016.png)

1. Insert your offers in the body of the message and send the delivery. For more on this, refer to [About outbound channels](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} (Campaign v8 documentation).

   The recipient received the offer for which they are eligible.

1. The recipient rejected the Canada offer, as shown in the proposition history.

   ![Recipient proposition history with the Canada snowmobile offer in Rejected status](assets/offer_typology_example_018.png)

1. Check the offers for which they are now eligible.

   We can see that no offers for Canada are chosen.

   ![Recipient Preview tab showing eligible offers New-York and Grand Canyon, with no Canada offer](assets/offer_typology_example_019.png)
