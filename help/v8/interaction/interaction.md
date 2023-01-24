---
title: Campaign Interaction - Offer management
description: Get started with Offer management
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
---
# Manage real-time interactions

Campaign comes with an **Interaction** module which lets you respond in real-time during an interaction to a given contact by proposing them a single or several specific offers. These offers can be simple communication messages, special offers on one or several products or a service.

You can create an offer catalog which interfaces with your outbound channels (email, direct mail, SMS) to select the best offer to send to a contact in a given context. Best offer selection for a recipient is based on **eligibility rules**. The selection of an offer from a set of relevant offers is determined using priority rules. Offer presentation rules consider the contact's history and help avoid having them receive the same offer several times.

Interaction lets you create and manage a catalog of offers, and configure the eligibility rules and application themes linked to them. Depending on the channel chosen, offer content can be personalized thanks to various rendering functions. Finally, you can use the simulation module to calculate the impact of an offer presentation.

![](assets/interaction-cycle.png)

First, a contact occurs between a customer and a company through a communication channel: it can be a website (outbound interaction), an email, SMS, push notification (inbound interactions). [Learn more](#interaction-types)

This contact results in a call to the Offer engine. (1)

When the call to the Offer engine happens, one or several offers are selected from the Offer catalog depending on the number of offers settings on the proposition. (2)

Then, eligibility rules are applied: best offers are selected based on the eligibility rules, start and end dates of offers,  profile data, and real-time behavior of the customer. (3)

The profile proposition history is updated once the selection is made, to avoid duplication of the offers that are presented. (4)

Finally, the best offer is proposed to the target. (5)

## Get started with offers

Key steps to start are listed below.

### Configure your platform

Before starting, as a Campaign **Administrator**, make sure you performed the following tasks in design environments:

1. Create user profiles. [Learn more](interaction-operators.md)
1. (optional) Create an offer environment for each targeting dimension. [Learn more](interaction-env.md)
1. Create typology rules for each environment. [Learn more](interaction-offer.md#offer-presentation)
1. Create offer spaces for each environment and configure rendering functions. [Learn more](interaction-offer-spaces.md)
  If the space is defined by a unitary channel on identified mode, you must specify the advanced parameters for this space.

   >[!NOTE]
   >
   >If the space is defined by a unitary channel on identified mode, you must specify the advanced parameters for this space.

1. Configure the Offer engine for inbound interactions to present and update one or several offers.

   The various integration modes are detailed in [this section](interaction-present-offers.md).

   >[!NOTE]
   >
   >When an offer space is created on the inbound Web channel, you must configure the website to display this offer.
   >

### Create and publish the offer catalog {#managing-the-offer-catalog-}

As an **Offer manager** you must:

1. Create offer categories in design environments. [Learn more](interaction-offer-catalog.md#creating-offer-categories)
1. Create offers in design environments. [Learn more](interaction-offer.md)
1. Approve and publish offers on one or several spaces to make them available on live environments for the delivery manager. [Learn more](interaction-offer.md#approve-offers)

### Use the offer catalog {#using-the-offer-catalog-}

As a **Delivery manager**  you must:

1. Create a campaign.
1. Reference an offer in the campaign or the delivery. [Learn more](interaction-send-offers.md).

## Glossary

Discover offer-specific terms and related guidance before starting.

* **Environment**: set which includes an offer catalog and hooks (offer spaces). Create one environment by targeting dimension. There are two types of environments:

    * **Design environment**: environment in which offers are created and/or typology rules are defined (rules that will determine the offers to present or not present to a targeted person). The table of individuals to be targeted by the offers and the table for storing all offer propositions are also defined in this. The **[!UICONTROL Design environment]** node contains offer space sub-folders, pre-defined filters, and offer categories. For every **[!UICONTROL Design environment]** there is one corresponding read-only **[!UICONTROL Live environment]**, generated from this same **[!UICONTROL Design environment]**.
    * **Live environment**: environment linked to a **[!UICONTROL Design environment]**. It contains read-only offers whose content and eligibility have been approved via the **[!UICONTROL Design environment]**. They are available to be displayed on a Web site or inserted into a message.

* **Offer space**: folder defining the location where the offer is exposed. When defining a space lets you can:
  * select the channel
  * choose it can be used in unitary mode (by default: only in batch mode)
  * build the content of the offer using rendering functions
  * specify the offers to present
  
  A space is an interface between the channel and the Offer engine.

  >[!CAUTION]
  >
  >An offer space is not a communication channel, it coincides with a specific exposition location on the channel. For example, offers exposed on a website can occupy two spaces on the same page. In this case, you have two spaces for the same channel.
  >
  >Spaces must be defined in the specifications and must not be modified during the project.

* **Offer catalog**: set of offers defined in Adobe Campaign that can be selected during an interaction. The catalog is organized hierarchically with each node corresponding to a category.
* **Category**: a folder linked to the offer catalog in an environment, which organizes offers based on nature, eligibility date and application theme. A category can contain sub-categories, which inherit all the characteristics of the parent category. Eligibility rules can be defined for a category as to share them for several offers.
* **Application themes**: keywords defined in the category, which let you filter offers when they are presented to an inbound or outbound channel by restricting the selection of offers to one or two categories.

  >[!NOTE]
  >
  >Child categories inherit the themes identified in the parent category.

* **Eligibility rules**: constraints applied to an environment, category, or offer concerning the validity period, target, and weight. They let you ensure that an offer is in line with the targeted contact.

  In the environments, eligibility rules include presentation rules applied to the offers and the people to target.

  In the categories, eligibility rules let you: limit the validity of the category in time, define application themes, and determine the people to target. They can also receive a multiplier weight for a given time. This lets you share the rules for offers in other categories and so simplifies managing them.

  In the offers, eligibility rules let you limit the validity of offers in time and determine the people to target.

* **Arbitrage**: selecting offers to display on an environment (eligible offers). The arbitrage principle ranks offers by priority according to the criteria defined in the categories, offers, and context offers.
* **Contact**: a contact from an inbound interaction. During engine call processing, the contact is associated to a targeting dimension. There are two types of contacts:

    * **[!UICONTROL Identified contact]** : a contact that has voluntarily been identified on the channel. In outbound interactions, the contact is automatically identified.
    * **[!UICONTROL Anonymous contact]** : a contact that has not voluntarily subscribed through the channel but can be implicitly identified through a cookie. This terminology is only used for incoming interactions.

      >[!NOTE]
      >
      >Non-identified, anonymous contacts are attributed to the visitor targeting dimension.

* **Outbound interaction**: call to the Offer engine from a contact list (used for delivering emails, direct mail, etc.). The same rules and processes are applied to each contact. This type of interaction is usually processed in batch mode.
* **Inbound interaction**: interaction following an incoming call generated by the action of a contact on the channel. This type of interaction is usually processed in unitary mode.
* **Batch mode**: the batch mode lets you select the best offer for a set of contacts. Eligibility/prioritization rules are applied to all of the contacts of the set. This mode is usually applied for outbound interactions.
* **Unitary mode**: a single contact is processed at a time. This mode is usually applied for inbound interactions and transactional messages.
* **Identification mode**: refers to the status of a contact:

    * **[!UICONTROL explicit]** : contacts are identified by their login onto the channel interface.
    * **[!UICONTROL implicit]** : contact are identified by a cookie (permanent or session). It can be processed as an anonymous or identified contact.
    * **[!UICONTROL anonymous]** : contacts cannot be identified.

* **Eligible offer**: offer meeting the constraints defined upstream that can be consistently offered to a target.
* **Presentation rules**: typology rules referenced in the offer environment, which let you exclude some offers by taking the proposition history into account.
* **Weight**: formulas that let you precisely calculate the relevance of an offer, to select the most relevant offer. Weights are defined in the offers. Eligible offers are taken into account in decreasing weight order.
* **Rendering function**: function defined in the offer space to construct its offer representation based on the attributes defined in the offer. There are three different rendering function modes: HTML, XML, and text.
* **Offer proposition**: result of the action which consists of presenting one or several offers to a contact in a given space (banner on a website, email or SMS for example). This result is stored in the offer propositions table. However, it is not mandatory to save the propositions.
* **Simulation**: module which lets you test the offer presentation on the targeted recipients before actually sending the offers.
* **Preview**: preview of the offer as it is displayed in its folder. It is accessible from the offer settings window or the contact profile.
* **pre-defined filters**: pre-defined filtering rules can take into account offer parameters (for example, an offer code). They can be reused after offers have been created.
* **Offer representation**: information used by the channel to display the offer. Offer representation may be constructed from the rendering function of the space on which the offer is represented or entered directly into the interface (for example, in the HTML block). An offer may be represented by space.
* **Changeover process**: an activated process in an identified environment, responsible for directing the call to an anonymous environment if the contact has not been explicitly and/or implicitly identified.
