---
title: Operators profiles
description: Create Offer management operators
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
TQID: https://experienceleague.adobe.com/0Nx5tAtCSIZ3Ctm8MHRU7Aa2-8CyX6IbDgj9RF5KlSI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Operators profiles {#operator-profiles}

Two types of operators can use Campaign Interaction: **Offer managers** and **Delivery managers**. Each of them has specific permissions and restrictions. Learn more about Campaign operators and permissions in [this page](../start/gs-permissions.md).

* The **[!UICONTROL Offer manager]** creates and maintains offers.
* The **[!UICONTROL Delivery manager]** approves and uses offers

## Create an Offer manager operator{#offer-manager}

1. Create an operator. [Learn more](../start/manage-permissions.md#add-users)
1. Browse to the **[!UICONTROL Groups and named rights]** window, click **[!UICONTROL Add]** and select the **[!UICONTROL Offer manager]** group.

Permissions associated to Offer managers are described [here](../start/manage-permissions.md#ootb-productprofiles)

## Create a Delivery manager operator {#delivery-manager}

1. Create an operator. [Learn more](../start/manage-permissions.md#add-users)
1. Browse to the **[!UICONTROL Groups and named rights]** tab, click **[!UICONTROL Add]** and select the **[!UICONTROL Delivery manager]** group.

The rights assigned to Delivery managers enable them to carry out the following tasks:

* Display **[!UICONTROL Live]** environments.
* Display and modify offer categories.
* Approve offers if they are their reviewers.

  >[!NOTE]
  >
  >**Delivery managers** can only approve an offer if they have been declared as reviewers in the offer configuration.

## Permission matrix per Interaction operator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Offer manager (Design environment)</strong><br /> </td> 
   <td> <strong>Offer manager (Live environment)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tree structure level</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offers being edited / Live offers<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient - Environment<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> pre-defined offer filters<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology rules<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Offer catalog<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Offer category<br /> </td> 
   <td> Read / Write<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Delivery manager (Design env.)</strong><br /> </td> 
   <td> <strong>Delivery manager (Live env.)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tree structure level</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offers being edited / Live offers<br /> </td> 
   <td> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Recipient - Environment<br /> </td> 
   <td> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> pre-defined offer filters<br /> </td> 
   <td> Read<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology<br /> </td> 
   <td> Read<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology rules<br /> </td> 
   <td> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Offer catalog<br /> </td> 
   <td> Read<br /> </td> 
   <td> Read<br /> </td> 
  </tr> 
  <tr> 
   <td> Offer category<br /> </td> 
   <td> </td> 
   <td> Read<br /> </td> 
  </tr> 
 </tbody> 
</table>
