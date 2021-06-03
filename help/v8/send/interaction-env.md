---
product: Adobe Campaign
title: Campaign Interaction operators
description: Create Offer management operators
feature: Overview
role: Data Engineer
level: Beginner
---
# Live and Design environments{#live-design-environments}

Interaction operates with two types of offer environments:

* **[!UICONTROL Design]** offer environments that include offers that are being edited and can be altered. These offers haven't been through the approval cycle and aren't delivered to contacts.
* **[!UICONTROL Live]** offer environments that include approved offers as they are presented to contacts. The offers in this environment are read-only.

![](assets/offer_environments_overview_001.png)

Each **[!UICONTROL Design]** environment is linked to a **[!UICONTROL Live]** environment. When an offer is complete, its content and eligibility rules are subjected to an approval cycle. Once this cycle is complete, the concerned offer is automatically deployed to the **[!UICONTROL Live]** environment. From this moment on, it will be available for delivery.

By default, Campaign comes with a **[!UICONTROL Design]** environment and a **[!UICONTROL Live]** environment linked to it. Both environments are pre-configured to target the [built-in recipient table](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>To target recipient table, you need to use the target mapping assistant to create the environments. [Learn more](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Delivery managers can only view the **[!UICONTROL Live]** environment and leverage offers to deliver them. Offer managers can view and use the **[!UICONTROL Design]** environment, and view the **[!UICONTROL Live]** environment. [Learn more](interaction-operators.md)

## Create an offer environment {#creating-an-offer-environment}

By default, Campaign comes with a built-in environment to target the recipient table (identified offers). To target another table, follow the steps below:

1. Browse to **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, right-click the target mapping you want to use and select **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Click **[!UICONTROL Next]**, select the **[!UICONTROL Generate a storage schema for propositions]** option and click **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >If the option is already checked, uncheck it then recheck it.

1. Adobe Campaign creates two environments - **[!UICONTROL Design]** and **[!UICONTROL Live]** - with targeting information from the previously enabled target mapping. The environment is preconfigured with the targeting information.
