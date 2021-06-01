---
product: Adobe Campaign
title: Campaign Interaction operators
description: Create Offer management operators
feature: Overview
role: Data Engineer
level: Beginner
---

# Operators profiles {#operator-profiles}

Two types of operators can use Campaign Interaction: **Offer managers** and **Delivery managers**. Each of them has specific permissions and restrictions. Learn more about Campaign operators and permissions in [this page](../start/permissions.md).

* The **[!UICONTROL Offer manager]** creates and maintains offers.
* The **[!UICONTROL Delivery manager]** approves and uses offers

## Create an Offer manager operator{#offer-manager}

1. Create a new operator. 

   [!DNL :arrow_upper_right:] Steps to create an operator in Campaign are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Go to the **[!UICONTROL Groups and named rights]** window, click **[!UICONTROL Add]** and select the **[!UICONTROL Offer manager]** group.

The rights assigned to the Offer manager enable them to carry out the following tasks:

* Modify **[!UICONTROL Design]** environments.
* View **[!UICONTROL Live]** environments.
* Configure administration functions (predefined spaces and filters).
* Create and alter categories.
* Create offers.
* Configure offer eligibility.
* Approve offers.

 Note that if offers are used in a workflow, the operator needs to be added to the **[!UICONTROL Administrator]** or **[!UICONTROL Offer managers]** operator group to execute the workflow.

  >[!NOTE]
  >
  >An **Offer manager** can only approve an offer if no reviewer is specified, or if he/she has been declared as the reviewer in the offer template on which the offer was based upon.

## Create a Delivery manager operator {#delivery-manager}

1. Create a new operator.
  
   [!DNL :arrow_upper_right:] Steps to create an operator in Campaign are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Go to the **[!UICONTROL Groups and named rights]** window, click **[!UICONTROL Add]** and select the **[!UICONTROL Delivery manager]** group.

The rights assigned to the Delivery manager are/enable them to carry out the following tasks:

* Display **[!UICONTROL Live]** environments.
* Display and modify offer categories.
* Approve offers if s/he is specified as one of its reviewers.

  >[!NOTE]
  >
  >A **Delivery manager** can only approve an offer if he/she has been declared as a reviewer during the offer configuration.

## Permission matrix per Interaction operator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Offer manager (Design env)</strong><br /> </td> 
   <td> <strong>Offer manager (Live env)</strong><br /> </td> 
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
   <td> Predefined offer filters<br /> </td> 
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
   <td> Predefined offer filters<br /> </td> 
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
