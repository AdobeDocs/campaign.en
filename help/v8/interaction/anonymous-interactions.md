---
product: campaign
title: Present offers to anonymous profiles (inbound interaction)
description: Learn how to present offers to anonymous profiles
role: User, Admin
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
---
# Anonymous interactions{#anonymous-interactions}

## Environment for anonymous interactions {#environment-for-anonymous-interactions}

By default, Campaign **Interaction** module comes with a pre-configured environment to target the built-in recipient table (identified offers). If you need to target another table, a visitor table for anonymous offers or a custom recipient table for example, you must use the target mapping wizard to create the environment. [Learn more about environments](interaction-env.md).

When you create an anonymous environment via the mapping creation wizard, the **[!UICONTROL Environment dedicated to incoming anonymous interactions]** box is automatically checked in the environment's **[!UICONTROL General]** tab.

The **[!UICONTROL Targeting dimension]** is automatically completed. By default, it links to the visitor table.

The **[!UICONTROL Visitor folder]** field appears. It is automatically completed to link to the **[!UICONTROL Visitors]** folder. This field lets you choose where to store visitor profiles. 

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>If you want to filter several types of visitors, for instance in the case of anonymous offers presented for one or more brands, you need to create an environment for each brand, and a **[!UICONTROL Visitors]** type folder for each environment.

## Offer catalog for anonymous interactions {#offer-catalog-for-anonymous-interactions}

Just like outbound interactions, inbound interactions are organized in an offer catalog which is made up of categories and offers.

To create categories and spaces, apply the same process as for identified visitors. Refer to [Create an offer category](interaction-offer-catalog.md#creating-offer-categories) and [Create an offer environment](interaction-env.md#creating-an-offer-environment)).

## Anonymous visitors {#anonymous-visitors}

Anonymous visitors may be submitted to a cookie identification process when they connect. This implicit recognition is based on the visitor's browser history.

During this step, a comparison is made between the data recovered by the cookies and those in your database. In some cases, visitors are recognized (they arethen implicitly identified), in other cases, they are not recognized (and therefore remains anonymous).

To run this analysis, for the offer space, check the **[!UICONTROL Implicitly identify the individual based on their browser history]** option.

![](assets/identification_anonymous_visitors.png)

## Processing unidentified anonymous visitors {#processing-unidentified-anonymous-visitors}

After analysis, if an anonymous visitor is not identified, you can store their data in a given space. This will allow you to suggest offers specifically aimed at this type of visitor, matching the specified typology rules.

If there is no element that allows you to identify a contact, or if you do not want to suggest an identified offer to a contact that can be implicitly identified, you can choose to carry out a fallback on an anonymous environment.

To do this, check the **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**, then specify the environment dedicated to these unidentified visitors in the **[!UICONTROL Linked anonymous space]** when specifying an offer space.

![](assets/anonymous_to_anonymous_environment.png)
