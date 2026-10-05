---
product: campaign
title: Message Center (Control)
description: Message Center (Control)
feature: Workflows
role: User
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
---

# Message Center (Control){#message-center-control}

The workflow detailed below is scheduled to run every hour. It is installed with the **Message Center - Control** module by default.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Message Center &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> This workflow:<br /> 
    <ul> 
     <li> <p>recovers the list of events processed by the operation(s).</p> </li> 
     <li> <p>synchronizes with the NmsBroadLogMsg table in order to recover delivery message qualifications.</p> </li> 
     <li> <p>recovers event delivery logs as soon as synchronization with the NmsBroadLogMsg table has been completed.</p> </li> 
     <li> <p>synchronizes with the NmsTrackingUrl table in order to recover the tracking for delivery URLs.</p> </li> 
     <li> <p>recovers event tracking URLs as soon as synchronization with the NmsTrackingUrl table has been completed.</p> </li> 
     <li> <p>lets you recover all email addresses placed in quarantine every three hours after a delivery has been sent.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

