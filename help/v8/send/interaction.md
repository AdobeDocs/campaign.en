---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Interaction - Offer management
description: Get started with Offer management
feature: Overview
role: Data Engineer
level: Beginner
---
# Interaction and offer management{#interaction-and-offer-management}

Campaign comes with an **Interaction** module which lets you respond in real time during an interaction with a given contact (a customer or target) by making them a single or several adapted offers. For example, these can be simple communication messages, special offers on one or several products or a service.

You can create an offer catalog that will interface with your outbound channels (email, direct mail, SMS) to select the best offer to send to a contact in a given context. Best offer selection for a recipient is based on **eligibility rules**. The selection of an offer from a set of relevant offers is determined using priority rules. Offer presentation rules take into account the contact's history and help avoid having them receive the same offer several times.

Interaction lets you create and manage a catalog of offers, and configure the eligibility rules and application themes linked to them. Depending on the channel chosen, offer content can be personalized thanks to various rendering functions. Finally, you can use the simulation module to calculate the impact of an offer presentation.

## Get started with offers

Key steps to start are listed below.

### Configure your platform

Before starting, as a Campaign **Administrator**, make sure you performed the following tasks in design environments:

1. Create user profiles. [Learn more](interaction-operators.md).
1. (optional) Create an offer environment for each targeting dimension. [Learn more](interaction-env.md)
1. Create typology rules for each environment. [Learn more](interaction-offer.md#offer-presentation).
1. Create offer spaces for each environment and configure rendering functions. [Learn more](interaction-offer-spaces.md).
  If the space is defined by a unitary channel on identified mode, you must specify the advanced parameters for this space.

### Create and publish the offer catalog {#managing-the-offer-catalog-}

As an **Offer manager** you need to perform the following tasks:

1. Create offer categories in design environments. [Learn more](interaction-offer-catalog.md#creating-offer-categories).
1. Create offers in design environments. [Learn more](interaction-offer.md).
1. Approve and publish offers on one or several spaces in order to make them available on live environments for the delivery manager. [Learn more](interaction-offer.md#approve-offers).

### Leverage the offer catalog {#using-the-offer-catalog-}

As a **Delivery manager**  you need to perform the following tasks:

1. Create a campaign.
1. Reference an offer in the campaign or the delivery. [Learn more](interaction-send-offers.md).


## Concepts and terminology

Discover offer-specific terms and related guidance before starting.

* **Environments** include an offer catalog and offer spaces (hooks). You need to create one environment by targeting dimension. 
  There are two types of environments:

    * **Design environment**: offers are created in the design environment, as well as and typology rules. Typology rules determine the offers to present (or not) to a targeted person. The table of individuals that will be targeted by the offers and the table for storing all offer propositions are also defined in this environment. The **[!UICONTROL Design environment]** node contains offer space sub-folders, pre-defined filters and offer categories. For every **[!UICONTROL Design environment]** there is one corresponding read-only **[!UICONTROL Live environment]**, generated from this same **[!UICONTROL Design environment]**.
    * **Live environment**: environment linked to a **[!UICONTROL Design environment]** which contains read-only offers whose content and eligibility have been approved via the **[!UICONTROL Design environment]**. They are to be selected to be presented inserted into a message.

* The **Offer space** is a location (folder) defining the location where the offer is exposed. When creating an offer space, you can specify the channel, build the content of the offer using rendering functions, specify the order of the offers, and its mode: unitary mode and/or batch mode (default). The offer space is the interface between the channel and the offer engine.
* THe **Offer catalog** is a set of offers defined in Adobe Campaign that can be selected during an interaction. The catalog is organized hierarchically with each node corresponding to a category.
* A **Category** is a folder linked to the offer catalog in an environment, which organizes offers based on nature, eligibility date and application theme. A category can contain sub-categories, which inherit all the characteristics of the parent category. Eligibility rules can be defined for a category as to share them for several offers.
* **Application themes** are keywords defined in the category, which let you filter offers when they are presented by restricting the selection of offers to one or two categories.
* **Eligibility rules** are constraints applied to an environment, category or offer, related the validity period, target and weight. They let you ensure that an offer is in line with the targeted contact.

  In the environments, eligibility rules include presentation rules applied to the offers and the people to target.

  In the categories, eligibility rules let you limit the validity of the category in time, define application themes and determine the people to target. They can also receive a multiplier weight for a given period of time. This lets you share the rules for offers in other categories and so simplifies managing them.

  In the offers, eligibility rules let you limit the validity of offers in time and determine the people to target.

* The **Arbitrage** is the action of selecting offers that will be shown on an environment (eligible offers). The arbitrage  ranks offers by priority according to the criteria defined in the categories, offers and context offers.
* An **Outbound interaction** calls the interaction engine from a contact list (used for delivering emails, direct mail, etc.). The same rules and processes are applied to each contact. This type of interaction is generally processed in batch mode.
* The **Batch mode** lets you select the best offer for a set of contacts. Eligibility/prioritization rules are applied to all of the set's contacts. This mode is generally used for outbound interactions.
* The **Unitary mode** lets you process a single contact at a time. This mode is generally used for transactional messages.
* **Eligible offers** are offers meeting the constraints defined upstream that can be consistently offered to a target.
* **Presentation rules** are typology rules referenced in the offer environment, which let you exclude some offers by taking the proposition history into account.
* **Weight** are formulas that let you precisely calculate the relevance of an offer, in order to select the most relevant offer. Weights are defined in the offers. Eligible offers are taken into account in decreasing weight order.
* **Rendering function** is defined in the offer space in order to construct its offer representation based on the attributes defined in the offer. There are three different rendering function modes: HTML, XML and text.
* **Offer proposition** is the result of the action which consists of presenting one or several offers to a contact in a given space (banner on a website, email or SMS for example). This result is stored in the offer propositions table. However, it is not mandatory to save the propositions.
* **Simulation** is a module which lets you test the offer presentation on the targeted recipients before actually sending the offers.
* The **Preview** of the offer shows the offer as it is displayed in its folder. It is accessible from the offer settings window or the contact profile.
* **Predefined filters** are filtering rules can take into account offer parameters (for example, an offer code). They can be reused after offers have been created.
* An **Offer representation** is an information used by the channel to display the offer. Offer representation may be constructed from the rendering function of the space on which the offer is represented or entered directly into the interface (for example, in the HTML block). An offer may be represented by space.

