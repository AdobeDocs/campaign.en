---
product: Adobe Campaign
title: Campaign Interaction Offer
description: Learn how to create an offer
feature: Overview
role: Data Engineer
level: Beginner
---
# Create an offer

To create an offer, follow the steps below:

1. Browse to the **[!UICONTROL Campaigns]** tab and click the **[!UICONTROL Offers]** link.

1. Click the **[!UICONTROL Create]** button.

1. Change the label and select the category the offer should belong to.

1. Click **[!UICONTROL Save]** to create the offer.

   The offer is available in the platform and its content can be configured.

## Eligibility settings 

You can now use the **[!UICONTROL Eligibility]** tab to define:

* The eligibility period of the offer. [Learn more](#eligibility-period)
* Filters on the offer target population. [Learn more](#filters-on-the-target)
* The offer weight. [Learn more](#offer-weight)

### Offer eligibility period{#eligibility-period}

In the **[!UICONTROL Eligibility]** tab of the offer, define the eligibility period of the offer. use the drop-down lists to select a start and an end date in the calendar.

![](assets/offer_eligibility_create_002.png)

Outside of this period, the offer will not be selected. If you have also configured eligibility dates for the offer category, the most restrictive period will apply.

### Add filters on the target {#filters-on-the-target}

In the **[!UICONTROL Eligibility]** tab of the offer, apply filters to the offer target.

To do this, click the **[!UICONTROL Edit query]** link and select the filter you want to apply. 

![](assets/offer_eligibility_create_003.png)

If predefined filters have been created already, you can select them from the list of user filters. [Learn more](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### Set the offer weight {#offer-weight}

To enable the engine to decide between several offers that the target is eligible for, you need to assign one or more weights to the offer. You can also apply filters to the target if necessary or restrict the offer space which the weight will apply to. An offer with a more significant weight will be preferred over an offer with less weight.

You can configure multiple weights for the same offer, for example to distinguish sup-periods, specific targets or even an offer space.

For example, an offer can have a weight of A for contacts aged 18 to 25 and a weight of B for contacts above that range. If an offer is eligible all summer, it can also have a weight of A in July and a weight of B in August.

>[!NOTE]
>
>The assigned weight can be temporarily modified according to the parameters of the category the offer belongs to. [Learn more](interaction-offer-catalog.md#creating-offer-categories)

To create a weight in an offer, apply the following steps:

1. In the **[!UICONTROL Eligibility]** tab of the offer, click **[!UICONTROL Add]**.

   ![](assets/offer_weight_create_001.png)

1. Change the label and assign a weight. Default value is 1.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >If no weight is entered (0), the target will not be considered eligible for the offer.

1. If you want the weight to apply for a given period, define eligibility dates.

   ![](assets/offer_weight_create_002.png)

1. If necessary, restrict the weight to a specific offer space. 

   ![](assets/offer_weight_create_003.png)

1. Apply a filter to a target.

   ![](assets/offer_weight_create_004.png)

1. Click **[!UICONTROL OK]** to save the weight.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >If a target is eligible for multiple weights for a selected offer, the engine keeps the best (highest) weight. When calling up the offer engine, an offer is selected a maximum of once per contact.

### Summary of offer eligibility rules {#a-summary-of-offer-eligibility-rules}

Once configuration is complete, a summary of the eligibility rules will be available on the offer dashboard.

To view it, click the **[!UICONTROL Schedule and eligibility rules]** link.

![](assets/offer_eligibility_create_005.png)

## Create the offer content {#creating-the-offer-content}

Use the **[!UICONTROL Content]** tab to define the offer content.

   ![](assets/offer_content_create_001.png)

1. Define the various parameters of the offer content.

    * **[!UICONTROL Title]** : Specify the title that you would like to make appear in your offer. Warning: this is not referring to the offer's label, which is defined in the **[!UICONTROL General]** tab.
    * **[!UICONTROL Destination URL]** : specify your offer's URL. It must start with "http://" or "https://".
    * **[!UICONTROL Image URL]** : specify a URL or an access path to the image of your offer.
    * **[!UICONTROL HTML content]** / **[!UICONTROL Text content]** : enter the body of your offer in the tab you would like. To generate tracking, the **[!UICONTROL HTML content]** must be composed of HTML elements that can be enclosed in a `<div>` type element. For example, the result of a `<table>` element in the HTML page will be as followed:

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Learn how to define the acceptance URL in [this section](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![](assets/offer_content_create_002.png)

   To find the required fields as they were defined during offer space configuration, click the **[!UICONTROL Content definitions]** link to display the list. [Learn more](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   In this example, the offer must include a title, an image, HTML content and a destination URL.

## Preview the offer {#previewing-the-offer}

Once the offer content is configured, you can preview the offer as it will appear for its recipient. 

To do this:

1. Click the **[!UICONTROL Preview]** tab.

   ![](assets/offer_preview_create_001.png)

1. Select the representation of the offer you want to view.

   ![](assets/offer_preview_create_002.png)

1. If you have personalized the offer content, select the offer target to view personalization.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## Approve and activate an offer{#approve-offers}

You can now approve and activate the offer to make it available in the **Live** environment.

[!DNL :arrow_upper_right:] For more on this, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

## Manage offer presentation{#offer-presentation}

Campaign lets you control the flow of offer propositions using presentation rules. These rules, which are specific to Campaign Interaction, are **typology rules**. They let you exclude offers based on the history of propositions already made to a recipient. They are referenced in the environment.

[!DNL :arrow_upper_right:] For more on this, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=en#managing-offers)

## Offer simulation

The Simulation module lets you test the distribution of offers belonging to a category or an environment before sending your proposition to recipients.

Simulation takes into account the contexts and eligibility rules previously applied to offers and their presentation rules. This lets you test and refine various versions of your offer proposition without actually using an offer or over/under soliciting a target, since simulation has no impact on the targeted recipients.

[!DNL :arrow_upper_right:] For more on Offer simulation, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.htm)
