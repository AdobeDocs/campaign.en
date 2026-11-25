---
product: campaign
title: Offers on an outbound channel
description: Offers on an outbound channel
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
---
# Offers on an outbound channel{#offers-on-an-outbound-channel}

 

## Email offer delivery {#email-offer-delivery}

In our database, there is a category of travel offers to Africa. The eligibility, contexts and representations of each offer have been configured. We now want to create a campaign to present our offers via email.

1. Create a marketing campaign and a targeting workflow.

   ![Targeting workflow of the Trips to Africa campaign: folder, delivery, deduplication and two list update activities](assets/offer_delivery_example_001.png)

1. Edit the email delivery and click the **[!UICONTROL Offers]** icon.

   ![Email delivery with the Offers icon opening the Offer management window, offer selection options and Offer space field](assets/offer_delivery_example_002.png)

1. Choose the email space for your offer environment that matches the holidays.

   ![Offer management window with the Offer space list showing the available email spaces, including Subscribers journeys](assets/offer_delivery_example_003.png)

1. Choose the category which contains the Africa travel offers.

   ![Offer management window with the Category tree expanded under Offer catalog and Journeys, Africa category highlighted](assets/offer_delivery_example_004.png)

1. Set the number of offers in the delivery to two.

   ![Offer management window with category Africa and Number of propositions per message set to 2](assets/offer_delivery_example_005.png)

1. Close the offer management window and create the content of your delivery. 

   ![Email delivery HTML content editor with the default include views, ready for offer propositions](assets/offer_delivery_example_006.png)

1. Use the menus to insert a first offer proposition and choose the HTML rendering function.

   ![HTML content toolbar menu: Propositions, then Proposition 1, Rendering function and HTML rendering](assets/offer_delivery_example_007.png)

1. Insert the second offer proposition.

   ![Email HTML content with both proposition include lines using the rendering/html view, before the unsubscription link](assets/offer_delivery_example_008.png)

1. Click **[!UICONTROL Preview]** to preview your offers in the delivery then select a recipient to preview the offers as they will receive them.

   ![Delivery Preview tab showing the email with the Crossing the Sahara offer title, text and image for a selected recipient](assets/offer_delivery_example_009.png)

1. Save your delivery and start the targeting workflow.
1. Open your delivery and click the **[!UICONTROL Audit]** tab of your delivery: you can see that the offer engine has selected the propositions to be made from the various offers in the catalog.

   ![Delivery Audit tab Log listing propositions generated per offer, such as the Pyramids and Sahara offers](assets/offer_delivery_example_010.png)

## Perform an offer simulation {#perform-an-offer-simulation}

1. In the **[!UICONTROL Profiles and Targets]** tab, click the **[!UICONTROL Simulations]** link, then click the **[!UICONTROL Create]** button.

   ![Simulations list with the Create button opening the New offer simulation dialog with template, label and folder](assets/offer_simulation_001.png)

1. Choose a label and specify the execution settings if necessary. 

   ![New offer simulation dialog with the label 1 year subscribers, the Simulations folder and execution settings](assets/offer_simulation_example_002.png)

1. Save the simulation. This then opens in a new tab.

   ![Simulation dashboard of 1 year subscribers with the Edit tab and a Start simulation button](assets/offer_simulation_example_003.png)

1. Click the **[!UICONTROL Edit]** tab, then **[!UICONTROL Scope]**.

   ![Simulation Edit tab, Scope section, with Environment or category, Offer space, Themes, Contact date and propositions](assets/offer_simulation_example_004.png)

1. Choose the category for which you want to simulate offers.

   ![Environment or category list expanded under Offers - design and Offer catalog, with the Travel category selected](assets/offer_simulation_example_005.png)

1. Choose the offer space to be used for the simulation.

   ![Offer space list under the Travel category offering Direct Mail and Email (Environment - Recipient)](assets/offer_simulation_example_006.png)

1. Enter validity dates. You must at least enter a start date. This lets the offer engine filter offers and choose those which are valid on a given date. 
1. If necessary, specify one or several themes to restrict the number of offers to those which contain this keyword in their settings.

   In our example, the **Travel** category contains two sub-categories with two separate themes. We want to run a simulation for offers with the **Customers>1 year** theme.

   ![Scope section with the Customer > 1 year theme entered in the Themes field for the Travel category](assets/offer_simulation_example_007.png)

1. Choose the recipients you want to target.

   ![Target selection filter wizard choosing A list of recipients, then the Frequent travellers list](assets/offer_simulation_example_008.png)

1. Configure the number of offers to be sent to each recipient.

   In our example, the offer engine will choose the 3 offers with the highest weight for each recipient.

   ![Scope section with Number of propositions set to 3 and the target query on the Special offer delivery list](assets/offer_simulation_example_009.png)

1. Save your settings, then click **[!UICONTROL Start]** in the **[!UICONTROL Dashboard]** tab to run the simulation.

   ![Dashboard Start simulation dialog asking for confirmation, with the OK button highlighted](assets/offer_simulation_example_010.png)

1. Once the simulation is finished, consult the **[!UICONTROL Results]** for a detailed breakdown of propositions per offer.

   In our example, the offer engine has based the offer breakdown on 3 propositions. 

   ![Simulation Results tab with Breakdown of propositions by offers: population size 30, number of propositions 30](assets/offer_simulation_example_011.png)

1. Display the **[!UICONTROL Breakdown of offers by rank]** to view the list of offers selected by the offer engine.

   ![Breakdown of offers by rank report with offer ranking table for Trip to the USA and Discover France, and a pie chart](assets/offer_simulation_example_012.png)

1. If necessary, you can change the scope settings and run the simulation again by clicking **[!UICONTROL Start simulation]**.

   ![Dashboard Start simulation dialog asking for confirmation, with the OK button highlighted](assets/offer_simulation_example_010.png)

1. To save the simulation data, use the history or export functions available in the report. 

   ![Breakdown of offers by rank report with the Export menu and the save icon highlighted](assets/offer_simulation_example_013.png)
