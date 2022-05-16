---
title: Operators profiles
description: Create Offer management operators
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
---
# Operators profiles {#operator-profiles}

Two types of operators can use Campaign Interaction: **Offer managers** and **Delivery managers**. Each of them has specific permissions and restrictions. Learn more about Campaign operators and permissions in [this page](../start/permissions.md).

* The **[!UICONTROL Offer manager]** creates and maintains offers.
* The **[!UICONTROL Delivery manager]** approves and uses offers

## Create an Offer manager operator{#offer-manager}

1. Create an operator. 

   ![](../assets/do-not-localize/book.png) Steps to create an operator in Campaign are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Go to the **[!UICONTROL Groups and named rights]** window, click **[!UICONTROL Add]** and select the **[!UICONTROL Offer manager]** group.

The rights assigned to the Offer manager enable them to carry out the following tasks:

* Modify **[!UICONTROL Design]** environments.
* View **[!UICONTROL Live]** environments.
* Configure administration functions (pre-defined spaces and filters).
* Create and alter categories.
* Create offers.
* Configure offer eligibility.
* Approve offers.

If offers are used in a workflow, the operator must be added to the **[!UICONTROL Administrator]** or **[!UICONTROL Offer managers]** operator group to execute the workflow.

  >[!NOTE]
  >
  >**Offer managers** can only approve an offer if no reviewer is specified, or if they have been declared as reviewers in the offer template.

## Create a Delivery manager operator {#delivery-manager}

1. Create an operator.
  
   ![](../assets/do-not-localize/book.png) Steps to create an operator in Campaign are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Go to the **[!UICONTROL Groups and named rights]** window, click **[!UICONTROL Add]** and select the **[!UICONTROL Delivery manager]** group.

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
