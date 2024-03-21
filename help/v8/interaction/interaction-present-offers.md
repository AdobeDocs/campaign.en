---
product: campaign
title: Present an offer (inbound interaction)
description: Learn how to present the best offer using Campaign Interaction module
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
---
# Present the best offer{#interaction-present-offers}

Offers can be presented on various offer spaces using [an inbound or outbound channel](interaction-architecture.md#interaction-types). This chapter details some specific features for inbound channels.

![](assets/inbound-interactions.png)

In order for an offer to be selected by the Offer engine, it has to be approved and be available in a live environment.

For more on this, refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html#approving-offer-content)

In the context of an inbound contact a contact, the user who is browsing the page can be identified by the website or not. The Offer engine presents different offers for identified profiles and for anonymous profiles.

Before being able to present offers on an inbound channel, you must configure the Offer engine call where you would like the offers to be presented. In most cases for an inbound interaction, this is the Web page.

>[!NOTE]
>
>For inbound interactions, you must specifically configure the Offer engine to present and update one or several offers.
>
>You also have to enable unitary mode on your offer spaces. For more on this, refer to [this page](interaction-offer-spaces.md).
