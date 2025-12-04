---
title: Delivery statuses
description: Learn more about the statuses available on your delivery dashboard
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
---
# Delivery statuses {#delivery-statuses}

Once a delivery has been sent, the delivery dashboard displays a status that allows you to monitor if the sending has been successful. Possible statuses are detailed in the section below.

![](assets/delivery-status.png)

For more details on the different delivery failures you can encounter, and how to solve them, refer to [Understanding delivery failures](delivery-failures.md).

**Related topics:**

* [Send and monitor your emails](send.md)
* [Understand delivery failures](delivery-failures.md)
* [Get started with deliverability](about-deliverability.md)

## List of delivery statuses {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Status<br /> </th> 
   <th> Definitions and solutions<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> The delivery was correctly sent to the message provider (but the recipient did not necessarily receive it).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignored<br /> </td> 
   <td> The delivery was not sent to the recipient because of an error with their address. It was either on denylist, quarantined, not provided or a duplicate. <br /> </td> 
  </tr> 
  <tr> 
   <td> Failed<br /> </td> 
   <td> The delivery could not reach the recipient because of an invalid address or a full inbox for example. It can also be linked to an issue with personalization blocks since they can generate errors when the schemas do not match the delivery mapping. See <a href="delivery-failures.md" target="_blank">Understanding delivery failures</a><br /> </td> 
  </tr>
  <tr> 
   <td> Pending<br /> </td> 
   <td> The delivery is ready to be sent and is going to be processed by the delivery server (MTA). See <a href="#pending-status" target="_blank">Pending status</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Not applicable<br /> </td> 
   <td> The delivery was taken into account by the server (MTA) but not processed.<br /> </td> 
  </tr>  
  <tr> 
   <td> Delivery canceled<br /> </td> 
   <td> The delivery was canceled by an operator.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taken into account by the service provider<br /> </td> 
   <td> For SMS deliveries, the SMS service provider received the delivery.<br /> For email deliveries, the message was successfully relayed from Campaign to the MTA (Mail Transfer Agent).</td> 
  </tr> 
  <tr> 
   <td> Received on mobile<br /> </td> 
   <td> The recipient received the SMS on their mobile device.<br /> </td> 
  </tr>
  <tr> 
   <td> Sent to the service provider<br /> </td> 
   <td> The delivery was sent to the SMS service provider but not received yet.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Prepared<br /> </td> 
   <td> Intermediary status used only for external connectors such as the mobile channel. It follows the 'Pending' status and is the external connector that will determine the following status.<br /> </td> 
  </tr> 
 </tbody> 
</table>

To learn how to optimize the deliverability of your Adobe Campaign emails, refer to [this section](about-deliverability.md). For a deeper dive on deliverability, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html).

## Pending status {#pending-status}

After confirming your delivery, you can see that the status of your delivery is **[!UICONTROL Pending]**. This status means that the execution process is waiting on the availability of some resources.

The **[!UICONTROL Pending]** status can first mean that your delivery has been scheduled and is pending until the given date. For more on this, refer to the [Schedule delivery sending](configure-and-send.md#schedule-delivery-sending) section.

If your delivery is not being sent and its status remains **[!UICONTROL Pending]**, it can be the result of:

* **Too many campaigns running simultaneously**
  
  The limit of simultaneous campaigns is defined in the **[!UICONTROL NmsOperation_LimitConcurrency]** option. Default value is 10.
  
  As a Managed Cloud Services user, you can work with Adobe to adjust this limit if needed. Learn more about options in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}.

* **Resource availability issues**

  The MTA (Message Transfer Agent) may be waiting for resources to become available before processing your delivery. 

>[!NOTE]
>
>As a Campaign v8 Managed Cloud Services user, the MTA infrastructure is monitored and managed by Adobe. If you experience persistent issues with pending deliveries, contact Adobe Customer Care.

**Related topics:**

* [Send and monitor your emails](send.md#email-monitoring)
* [Understand delivery failures](delivery-failures.md)
* [Monitor your Campaign environment](../start/monitor.md#monitor-deliveries)

