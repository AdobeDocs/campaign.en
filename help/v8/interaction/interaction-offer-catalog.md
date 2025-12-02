---
title: Campaign Interaction Offer catalog
description: Learn how to create an offer catalog
feature: Interaction, Offers
role: Developer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
---
# Create an offer catalog

As an **Offer manager**, you are responsible for creating the offer catalog.

An offer catalog is associated to a single pre-existing environment. Offers in this catalog can only be associated with the spaces specified in this same environment.

Before creating your offers, you must first specify an [environment](interaction-env.md) which contains all the characteristics (eligibility, constraints on the target, presentation rules) of a set of offers, sorted into categories, as well as the list of their spaces.

## Create offer categories{#creating-offer-categories}

Offer are organized into categories/sub-categories. Categoies are created in the **[!UICONTROL Design]** environment, and deployed automatically in the **[!UICONTROL Live]** environment (i.e. made available) when the offers they contain are approved. The **[!UICONTROL Design]** environment contains a default category to receive all offers. Sub-categories can be created to add hierarchy to the catalog offers.

For each category, you can define **eligibility dates**, which is the period during which the offers contained in the category can be presented to their target. You can also adjust the weight of a category to prioritize the offer presentation.

To create an new category, follow the steps below:

1. Browser to the **[!UICONTROL Offer catalog]** folder.

   ![](assets/offer_cat_create_001.png)

1. Right click and select **[!UICONTROL Create a new "Offer category" folder]** from the drop-down list.

   ![](assets/offer_cat_create_002.png)

1. Re-name the category. You can edit the label later using the **[!UICONTROL General]** tab.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Repeat these steps to create as many categories as necessary.

   Thereafter, as needed you can:

    * Assign eligibility dates from the **[!UICONTROL Eligibility]** tab.
    
      ![](assets/offer_cat_create_004.png)

    * **[!UICONTROL Edit query]** to apply filters to the offer target.

    * A recap of the eligibility rules.To view them, click the **[!UICONTROL Schedule and eligibility rules of the offer]** link.

## Add a fallback category

In order to ensure that all recipients receive an offer proposition, it is possible to systematically add one or various offer categories in the recommendations. 

These fallback offers must have a low (but non-null) weight, so that they are only taken into account if no higher weight offers is eligible. 

In addition, there must be no presentation rule applied to these offers to ensure that they are always included in the recommendations. This means that, during a proposition, if no higher weight offer is available, the recipient will receive at least one offer from this category.

To include a fallback category in the recommendations, follow the steps below:

1. Browse to your offer catalog.
1. Click the **[!UICONTROL Eligibility]** tab and select the **[!UICONTROL Always include this category in the recommendations]** option.
1. Click **[!UICONTROL Save]**.

   ![](assets/offer_cat_default_001.png)
