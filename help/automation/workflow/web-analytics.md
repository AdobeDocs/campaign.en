---
product: campaign
title: Web Analytics
description: Learn more about the Web Analytics package
feature: Workflows, Analytics Integration
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
    internal-label: Analytics integration
---

# Web Analytics{#web-analytics}



The workflows detailed below are installed with the **Web Analytics connectors** module by default.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Sending of indicators and campaign attributes</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span> <br /> </td> 
   <td> This workflow lets you send email campaign indicators from Adobe Campaign to Adobe Experience Cloud Suite via the Adobe&reg; Analytics connector. The indicators concerned are as follows: <strong>Sent</strong> (iSent), <strong>Total count of opens</strong> (iTotalRecipientOpen), <strong>Total number of recipients who clicked</strong> (iTotalRecipientClick), <strong>Errors</strong> (iError), <strong>Opt-Out</strong> (opt-out) (iOptOut).<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Identification of converted contacts</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span> <br /> </td> 
   <td> This workflow indexes site visitors that have completed their purchase after a re-marketing campaign. The data recovered by this workflow can be accessed in the <span class="uicontrol">Re-marketing efficiency report</span> (Refer to this ). <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Event purge</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span> <br /> </td> 
   <td> This workflow lets you delete every event from the database field according to the period configured in the <span class="uicontrol">Lifespan</span> field. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Recovery of web events</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span> <br /> </td> 
   <td> Every hour, this workflow downloads segments on internet user behavior on a given site, puts them into the Adobe Campaign database and launches the re-marketing workflow. <br /> </td> 
  </tr> 
 </tbody> 
</table>

