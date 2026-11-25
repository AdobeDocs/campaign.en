---
product: campaign
title: Creating hypotheses
description: Learn how to create hypotheses in Campaign Response Manager
feature: Campaigns
version: Campaign v8, Campaign Classic v7
audience: campaign
content-type: reference
topic-tags: response-manager
exl-id: e0b3bc9f-5e81-463f-a59e-cd972a47109b
TQID: 'https://experienceleague.adobe.com/FggklU5pqlhjpHlUpd6C2G3Cb0A0dsooRZo9iEya858'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: d72afaa0-c842-48c8-9a3c-51b7911edc1b
    internal-label: Response Management
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Create hypotheses{#creating-hypotheses}

 

There are various possibilities for creating/linking hypotheses to a campaign offer or delivery:

* Via the **[!UICONTROL Measurement hypotheses]** folder by creating a new hypothesis based on an existing template and linking it to an existing delivery.
* Via the **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** tab in a campaign.
* Via the **[!UICONTROL Measurement]** option of a delivery created from a campaign.

Hypotheses can only be calculated once the marketing campaign has been launched and recipients have received the delivery. If the hypothesis is based on an offer proposition, the latter needs to at least be presented and still be active. Offer and delivery hypotheses are created via the **[!UICONTROL Measurement hypotheses]** folder and are based on a hypothesis template. However, it is possible to reference a hypothesis directly in the delivery or the campaign before the campaign starts. In this case, the hypotheses will be calculated automatically once the marketing campaign is launched, based on execution settings. [Learn more](hypothesis-templates.md#hypothesis-template-execution-settings)

## Create a hypothesis on the fly on a delivery {#creating-a-hypothesis-on-the-fly-on-a-delivery}

To create a hypothesis on an existing delivery, apply the following process:

>[!NOTE]
>
>This operation is only possible for pending deliveries.

1. In the Adobe Campaign tree, go to **[!UICONTROL Campaign management > Measurement hypotheses]**.
1. Click the **[!UICONTROL New]** button or right-click on the list of hypotheses and select **[!UICONTROL New]** in the drop-down list.

   ![Measurement hypotheses list with the New button and the New hypothesis dialog for choosing a template](assets/response_hypothesis_instance_creation_002.png)

1. In the hypothesis window, select a previously created template. [Learn more](hypothesis-templates.md)

   ![New hypothesis dialog with the Hypothesis template drop-down listing the available templates](assets/response_hypothesis_instance_creation_003.png)

   The hypothesis context as it was defined in the selected model is displayed in the window.

   >[!NOTE]
   >
   >Settings defined in the template and not visible at this step are also kept in the memory and reassigned to the hypothesis in progress.

   ![New hypothesis dialog showing the query inherited from the selected template and the Delivery field](assets/response_hypothesis_instance_creation_004.png)

1. Select the delivery for which you want to create a hypothesis.

   ![New hypothesis dialog with the Delivery drop-down listing deliveries to select](assets/response_hypothesis_instance_creation_005.png)

1. You can personalize your hypothesis by editing the **[!UICONTROL General]**, **[!UICONTROL Transactions]** and **[!UICONTROL Scope]** tabs. [Learn more](hypothesis-templates.md#creating-a-hypothesis-model)
1. Start the hypothesis by clicking **[!UICONTROL Start]**.

   A workflow is automatically created to perform the measurement. The name is automatically defined depending on the hypothesis configuration.

   >[!CAUTION]
   >
   >You can access this if you have checked the **[!UICONTROL Keep execution workflow]** box.  
   >This option must be activated for debugging purposes only, in case of error while running the hypothesis. Workflows generated automatically are saved in the **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Objects created automatically]** > **[!UICONTROL Campaign workflows]** folder in the Adobe Campaign explorer. 
   > 
   >In addition, workflows generated automatically must not be modified. Any eventual modification would not be taken into account elsewhere for later calculations. 
   >
   >If you have checked this option, delete the workflow after it has executed.

   ![Start button of the Measurement hypotheses list and the confirmation prompt to start the hypothesis](assets/response_hypothesis_instance_creation_006.png)

   Once calculation is complete, measurement indicators are updated automatically.

   ![Hypothesis General tab with the indicators calculated by the hypothesis, such as response rate and reactions](assets/response_hypothesis_instance_creation_007.png)

1. If necessary, change the settings and re-start the hypothesis.

## Reference a hypothesis in a campaign delivery {#referencing-a-hypothesis-in-a-campaign-delivery}

You can reference a hypothesis in a marketing campaign before it is started. In this case, the hypothesis will be launched automatically once the delivery is sent, based on the execution settings defined in the hypothesis template. To create a hypothesis in a delivery, apply the following process:

1. Depending on your needs, you can create one or more **[!UICONTROL Delivery]** type templates, as described in [Create a hypothesis model](hypothesis-templates.md#creating-a-hypothesis-model)
1. Create a marketing campaign and targeting workflows.
1. In the delivery window, click the **[!UICONTROL Delivery measurement]** icon.
1. Select the hypothesis template (the query configured in the model is displayed in the hypothesis window).

   The hypothesis will be calculated automatically once the campaign is finished, based on the dates configured in the model. [Learn more](hypothesis-templates.md#hypothesis-template-execution-settings)

   ![Delivery measurement window with the Add button to reference a hypothesis template in a delivery](assets/response_hypothesis_instance_creation_008.png)

## Add a default hypothesis to deliveries for a campaign {#adding-a-default-hypothesis-to-deliveries-for-a-campaign}

You can directly reference a hypothesis at campaign level. In this case, the hypothesis will be automatically linked to all the deliveries created in the campaign. To do this:

1. Go to the **[!UICONTROL Edit]** tab of the campaign.
1. In the measurement section, click the **[!UICONTROL Default hypotheses]** tab.

   ![Campaign Edit tab, Measurement section, with the Default hypotheses tab highlighted](assets/response_hypothesis_instance_creation_010.png)

1. Click **[!UICONTROL Add]** and select a hypothesis template.

   ![Add a hypothesis dialog with the template drop-down on the Default hypotheses tab of a campaign](assets/response_hypothesis_instance_creation_011.png)

   A hypothesis based on this template will now be referenced by default in each new delivery for the campaign.

   ![Delivery measurement window in a targeting workflow listing Hypothesis on purchases](assets/response_hypothesis_instance_creation_012.png)

The hypothesis results can be viewed in the **[!UICONTROL General]** and **[!UICONTROL Reactions]** tabs of the hypothesis. [Learn more](hypothesis-tracking.md)

For more information, you can also refer to [this sample](#example--creating-a-hypothesis-linked-to-a-delivery).

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

Creating a hypothesis on an offer proposition is similar to creating an on the fly delivery hypothesis. The hypothesis can be executed as long as the offer is active. The calculation period is based on the offer proposition date. When the hypothesis lets you link a recipient to a purchase, the status of the offer proposition likely to be accepted can be changed automatically. [Learn more](hypothesis-templates.md#transactions)

1. Create one or more **[!UICONTROL Offer]** type models as described in [Create a hypothesis model](hypothesis-templates.md#creating-a-hypothesis-model).
1. Go to the **[!UICONTROL Campaign management > Measurement hypotheses]** node.
1. Create an **[!UICONTROL Offers]** type hypothesis by selecting the model created previously.

   ![New hypothesis dialog with the template drop-down listing offer templates such as New offer hypothesis](assets/response_hypothesis_instance_offer_001.png)

   The query created in the model appears in the window.

   ![New hypothesis dialog with the Offer Hypothesis template and the query type equal to Item](assets/response_hypothesis_instance_offer_003.png)

1. Choose the offer for which you want to create a hypothesis.

   ![New hypothesis dialog with the Offer drop-down listing offers such as Trip to Paris](assets/response_hypothesis_instance_offer_004.png)

1. Refine the query if necessary.
1. Click **[!UICONTROL Start]** to run the hypothesis.
1. The hypothesis results can be viewed in its **[!UICONTROL General]** and **[!UICONTROL Reactions]** tabs. [Learn more](hypothesis-tracking.md)

   Hypotheses made on an offer are referenced in the **[!UICONTROL Measurement]** tab.

   ![Offer Measure tab with the list of hypotheses linked to the offer under Calculation of effective ROI](assets/response_hypothesis_instance_offer_007.png)

   If the **[!UICONTROL Update offer proposition status]** option was enabled in the hypothesis template, the status of the offer proposition is changed automatically, thereby providing feedback on the impact of the campaign (for more on this, refer to [Transactions](hypothesis-templates.md#transactions)).

## Example: create a hypothesis linked to a delivery {#example--creating-a-hypothesis-linked-to-a-delivery}

In this example, we want to create a hypothesis linked to a delivery. This hypothesis will be based on the model created previously. [Learn more](hypothesis-templates.md#example--creating-a-hypothesis-template-on-a-delivery)

We will then refine the query inherited from the model to make a hypothesis on a specific article of the purchase table.

1. Create a campaign and a delivery. Refer to the [Campaign v8 documentation](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html){target=_blank}.

   In our example, we will use a direct mail type delivery.

1. Configure a seed address: the previously created hypothesis template was configured to take a control group into account in the reaction results.

   ![Campaign Advanced settings, Control population tab, with the control group configuration enabled](assets/response_hypothesis_delivery_example_007.png)

   >[!NOTE]
   >
   >For more information, refer to the [Campaign v8 documentation](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html#add-a-control-group){target="_blank"}.

1. Open the **[!UICONTROL Direct mail delivery]** and click the **[!UICONTROL Delivery measurement]** icon, then click **[!UICONTROL Add]**.

   ![Delivery measurement window of a direct mail delivery with the Add button for hypotheses](assets/response_hypothesis_delivery_example_002.png)

1. Choose the previously created hypothesis template from the drop-down list.

   ![Add a hypothesis dialog with the template drop-down listing Hypothesis on Purchase (HYP4)](assets/response_hypothesis_delivery_example_004.png)

   The query created in the model is displayed.

   ![New hypothesis dialog with the Hypothesis by ticket line template and its query Filter by product](assets/response_hypothesis_delivery_example_005.png)

1. Click **[!UICONTROL Edit query...]** and refine the query by entering the product that the hypothesis will concern.

   ![Edit query window filtering the hypothesis on the product name equal to Clothing](assets/response_hypothesis_delivery_example_006.png)

   You can check that the hypothesis is linked to the delivery in the **[!UICONTROL Edit]** > **[!UICONTROL Measurement]** tab of the campaign.

   ![Campaign Measurement section, Measurement hypotheses tab, listing Hypothesis on purchases for a delivery](assets/response_hypothesis_delivery_example_008.png)

1. Launch your targeting workflow and run the necessary checks until the campaign is finished. Refer to the [Campaign v8 documentation](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html#start-a-delivery){target=_blank}.

   ![Campaign dashboard with a direct mail delivery in progress and its status, target population and proofs](assets/response_hypothesis_delivery_example_009.png)

1. In the Adobe Campaign tree, go to the **[!UICONTROL Campaign management > Measurement hypotheses]** node to check the indicators calculated by the hypothesis.

   ![Measurement hypotheses list and General tab with the calculated indicators, such as contacted response rate](assets/response_hypothesis_delivery_example_010.png)
