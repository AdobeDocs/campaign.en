---
product: campaign
title: Campaign
description: Campaign
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---

# Campaign{#campaign}

The workflows detailed below are installed with the **Campaign** module by default. 

>[!CAUTION]
>
>These workflows MUST be started in order for the campaign processes to be executed at a campaign level.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Cost calculation</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> This workflow starts the calculation of expense and cost lines on the budgets, plans, programs, campaigns, deliveries and tasks.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Stock: Orders and alerts</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> This workflow launches stock calculation on the order lines and manages warning alerts thresholds.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Jobs on deliveries in campaigns</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> This workflow triggers the approved deliveries and starts post-processing the service provider for an external delivery. It also sends approval notifications and reminders.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Campaign jobs</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> This workflow manages the jobs for marketing campaigns (launches targeting, file extraction, etc.). It also creates workflows related to recurring and periodic campaigns.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Jobs on service providers</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> This workflow starts processing the provider (email to the router and post-processing) once deliveries have been approved. <br /> </td> 
  </tr> 
 </tbody> 
</table>

