---
product: campaign
title: Deliveries
description: Learn more about default Deliveries workflows
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
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

# Deliveries{#deliveries}



The workflows detailed below are installed with the **Deliveries** module by default.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reporting aggregates</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> This workflow updates aggregates used in reports. It is triggered every day at 2am by default.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Billing</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> This workflow sends the system activity report to the 'billing' operator by email. It is triggered the 25th of every month by default.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Alias cleansing</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleansing</span> <br /> </td> 
   <td> This workflow standardizes enumeration values. It is triggered every day at 3am by default.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> This workflow lets you create the list of bounce mail qualification rules, as well as the list of domains and MXs in the platform. This workflow only works if the HTTPS port is open. These lists are not updated unless the Deliverability module is installed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>This workflow is the database maintenance workflow: it makes different calculations from the statistics and processes, and deletes obsolete data from the database according to the defined configuration in the deployment assistant. It is triggered every day at 4am by default.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Paused workflows cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPausedWorkflows</span> <br /> </td> 
   <td> <p>This workflow analyzes paused workflows that have severity set to normal and triggers warnings and notifications when they have been paused for too long. After a month, paused technical workflows are stopped unconditionally. By default, it is triggered every Monday at 5 am.</p> <p>For more information, refer to Handling of paused workflows</a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Offer notification</span> <br /> </td> 
   <td> <span class="uicontrol">offerMgt</span> <br /> </td> 
   <td> This workflow deploys approved offers onto the online environment, as well as every category contained in the offer catalog.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Forecasting</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> This workflow analyzes deliveries saved in the provisional calendar (creates provisional logs). It is triggered every day at 1am by default.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Tracking</span> <br /> </td> 
   <td> <span class="uicontrol">tracking</span> <br /> </td> 
   <td> This workflow performs the recovery and consolidation of tracking information. It also assures the recalculation of tracking and delivery statistics, especially those used by Message Center archiving workflows. By default, it is triggered once per hour. <br /> </td> 
  </tr> 
 </tbody> 
</table>

