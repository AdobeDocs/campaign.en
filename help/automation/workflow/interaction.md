---
product: campaign
title: Interaction
description: Interaction
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
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

# Interaction{#interaction}

The workflows detailed below are installed with the **Offer engine (Interaction)** add-on by default. 

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Full aggregate calculation (propositionrcp cube)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> This workflow updates the <strong>Full</strong> aggregate for the <strong>Offer proposition</strong> cube. It is triggered every day at 6am by default. This aggregate captures the following dimensions: Channel, Delivery, Marketing Offer and Date.<br /> The <strong>Offer proposition</strong> cube is then used to generate reports based on offers.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter full aggregate calculation</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> This workflow updates the <strong>Full</strong> aggregate for the <strong>Message center</strong> cube. It is triggered every day at 3am by default. This aggregate captures the following dimensions: Channel, Date, Status and Event type.<br /> The <strong>Message center</strong> cube is then used to generate reports based on events. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Learn more about cubes and aggregates in [this section](../../v8/reporting/gs-cubes.md). 

