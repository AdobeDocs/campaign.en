---
title: Monitor your deliveries in Campaign UI
description: Learn how to access the list of deliveries and use the delivery dashboard to monitor your deliveries
feature: Monitoring
role: User
level: Beginner
---
# Monitor your deliveries in Campaign UI {#delivery-dashboard}

Monitoring your deliveries is essential to ensure your campaigns are efficient and reach your customers. Adobe Campaign provides you with tools to access your deliveries and monitor their performance through the delivery list and the delivery dashboard.

## Access the list of deliveries {#list-of-deliveries}

You can access deliveries from the delivery list, via the **[!UICONTROL Campaign Management > Deliveries]** node of the tree.

![](assets/deliveries-list.png)

By default, the list of deliveries contains the names and statuses of the deliveries created in the selected node. It also shows the number of messages to send, processed and sent with success.

* The number of **[!UICONTROL Messages to send]** corresponds to the number of recipients targeted after analysis and prior to delivery.
* The number of messages in the **[!UICONTROL Success]** column corresponds to the number of messages sent by the server and received by the recipients.
* The number of **[!UICONTROL Processed]** messages corresponds to the number of messages received plus the number of messages with errors.

>[!NOTE]
>
>For large deliveries, you may wish to update these values. To do this, select the delivery in question and then right-click it. Select **[!UICONTROL Action > Recompute delivery and tracking indicators...]** and then use the assistant to update this information.

## Delivery dashboard overview {#delivery-dashboard-overview}

The **delivery dashboard** is key to monitor your deliveries and eventual issues encountered during the sending of messages.

It allows you to retrieve information on a delivery and edit it if necessary. Note that tab contents may no longer be changed once the delivery has been sent.

Here are the information you can monitor using the several tabs that are available in the dashboard:

* [Delivery summary](#delivery-summary)
* [Delivery reports](#delivery-reports)
* [Delivery logs, mirror pages, exclusions](#delivery-logs-and-history)
* [Delivery tracking logs and history](#tracking-logs)
* [Delivery rendering](#delivery-rendering)
* [Delivery audit](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Related topics:**

* [Understand delivery failures](delivery-failures.md)
* [Quarantine management](quarantines.md)
* [Delivery best practices](../start/delivery-best-practices.md)
* [Managing deliverability](about-deliverability.md)

## Delivery summary {#delivery-summary}

The **[!UICONTROL Summary]** tab contains the characteristics of the delivery: delivery status, channel used, information about the sender, subject, information concerning execution.

## Delivery reports {#delivery-reports}

The **[!UICONTROL Reports]** link, which is accessible from the **[!UICONTROL Summary]** tab, lets you look at a set of reports related to the delivery action: general delivery report, detailed report, delivery report, distribution of failed messages, opening rate, clicks and transactions, etc.

The contents of this tab can be configured according to your requirements. For more on delivery reports, refer to [this section](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Delivery logs, history and exclusions {#delivery-logs-and-history}

The **[!UICONTROL Delivery]** tab gives a history of the occurrences in this delivery. It contains the delivery logs, i.e. the list of messages sent and their status and the associated messages.

For a delivery, you can display (for example) only recipients with a failed delivery or an address in quarantine. To do this, click the **[!UICONTROL Filters]** button and select **[!UICONTROL By state]**. Then select the state in the drop-down list. Various statuses are listed in the [delivery statuses page](delivery-statuses.md).

>[!NOTE]
>
>The list displaying the delivery logs can be customized, as any list in Campaign. You can, for example, add a column to know which IP address sent each email in a delivery. For more on configuring list display, refer to [this section](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

The **[!UICONTROL Display the mirror page for this message...]** link lets you view the mirror page for the contents of the delivery selected from the list in a new window.

The mirror page is available only for deliveries for which HTML content has been defined. For more on this, refer to [Link to the mirror page](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Delivery tracking logs and history {#tracking-logs}

The **[!UICONTROL Tracking]** tab lists the tracking history for this delivery. This tab displays tracking data for the messages sent, i.e. all URLs subject to tracking by Adobe Campaign. The tracking data is updated hourly.

>[!NOTE]
>
>If tracking is not enabled for a delivery, this tab is not displayed.

Tracking configuration is performed at the appropriate stage in the delivery assistant. See [How to configure tracked links](tracking.md).

**[!UICONTROL Tracking]** data is interpreted in the delivery reports. See [this section](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Inbox rendering {#delivery-rendering}

The **[!UICONTROL Inbox rendering]** tab allows you to preview the message in the different contexts in which it may be received and check the compatibility in major desktops and applications.

This way, you can make sure that your message will be displayed to the recipients in an optimal way on a variety of web clients, web mails and devices.

For more on inbox rendering, refer to [this page](inbox-rendering.md)


## Delivery audit {#delivery-audit-}

The **[!UICONTROL Audit]** tab contains the delivery log and all the messages concerning the proofs.

The **[!UICONTROL Refresh]** button lets you update the data. Use the **[!UICONTROL Filters]** button to define a filter on the data.

Special icons enable you to identify errors or warnings. See [Delivery analysis](delivery-analysis.md).

The **[!UICONTROL Proofs]** sub-tab lets you view the list of proofs that have been sent.

![](assets/s_ncs_user_delivery_log_tab.png)

You can modify the information displayed in this window (and that of the **[!UICONTROL Delivery]** and **[!UICONTROL Tracking]** tabs) by selecting the columns to be displayed. To do this, click the **[!UICONTROL Configure list]** icon located in the lower right-hand corner. For more on configuring list display, refer to [this section](../config/ui-settings.md#customize-lists).

## Delivery dashboard synchronization {#delivery-dashboard-synchronization}

From your delivery dashboard, you want to check the processed messages and delivery logs to be sure that your delivery was successfully sent.

Some indicators or status can be incorrect or not up-to-date, this may be resolved with the following solutions:

* If your delivery status is incorrect, check that all necessary approvals have been done for this delivery or that the **[!UICONTROL operationMgt]** and **[!UICONTROL deliveryMgt]** technical workflows are running without errors. 

* If your delivery counter does not match your delivery, try to recompute the indicators by right-clicking the relevant delivery in the Adobe Campaign explorer and selecting **[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]** to resynchronize. For more information on tracking indicators, refer to this [section](../reporting/delivery-reports.md#tracking-indicators).

You can also track your deliveries with different reports via the delivery dashboard. For more on this, refer to this [section](../reporting/delivery-reports.md).

>[!NOTE]
>
>As a Campaign v8 Managed Cloud Services user, the infrastructure is monitored and managed by Adobe. If you experience persistent issues with delivery indicators or dashboard synchronization, contact Adobe Customer Care.

