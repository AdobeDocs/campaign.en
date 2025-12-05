---
title: Adobe Campaign built-in delivery reports
description: Adobe Campaign built-in delivery reports
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
---
# Delivery reports {#delivery-reports}

You can track the execution of deliveries via various reports accessible from the delivery overview. 

To access reports, follow the steps below:

1. Browse to the **[!UICONTROL Campaigns]** tab and click the **[!UICONTROL Delivery]** link to display the list of deliveries.
1. Click the name of the delivery which reports you want to access. 
1. Select the **[!UICONTROL Summary]** tab and click the **[!UICONTROL Reports]** link to access the reports specific to the delivery.

   ![](assets/detailed-report-2.png)

   By default, the following reports are available:

    * **[!UICONTROL Delivery throughput]** 
    * **[!UICONTROL Sharing to social networks]**
    * **[!UICONTROL Statistics on sharing activities]**
    * **[!UICONTROL Hot clicks]**
    * **[!UICONTROL Tracking statistics]**
    * **[!UICONTROL URLs and click streams]**
    * **[!UICONTROL Tracking indicators]**
    * **[!UICONTROL Non-deliverables and bounces]**
    * **[!UICONTROL User activities]**
    * **[!UICONTROL Delivery summary]**
    * **[!UICONTROL Subscription tracking]**
    * **[!UICONTROL Delivery statistics]**
    * **[!UICONTROL Breakdown of opens]** 

## Tracking indicators {#tracking-indicators}

This report combines the key indicators for tracking the behavior of recipients upon receiving the delivery. It gives access to delivery and reception statistics, open and click-through rates, generated click streams, as well as sharing activities to social networks.

>[!NOTE]
>
>Values calculated based on message opens are always estimates, due to the margin of error linked to emails in text format. The **[!UICONTROL Distinct opens/Sum of opens for the population reached]** indicators take this margin of error into account. [Learn more](metrics-calculation.md#tracking-opens-).

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]**: Total number of messages to be delivered after delivery analysis.
* **[!UICONTROL Success]**: Number of messages successfully processed.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>The related percentages are calculated based on the number of messages forwarded successfully.

* **[!UICONTROL Distinct opens for the population reached]**: Estimation of the number of targeted recipients having opened a message at least once. Clicks on tracked URLs are taken into account since emails have to be opened to click on a link.
* **[!UICONTROL Sum of opens for the population reached]**: Estimation of the total number of opens by targeted recipients. 
* **[!UICONTROL Clicks on opt-out link]**: Number of clicks on the unsubscription link.
* **[!UICONTROL Clicks on the mirror page link]**: Number of clicks on the link to the [mirror page](../send/mirror-page.md). In order to be taken into account, the link must be defined as such in the delivery wizard (tracked URLs).
* **[!UICONTROL Estimation of forwards]**: Estimation of the number of emails forwarded by the targeted recipients. This value is calculated by subtracting the number of distinct people and the number of distinct recipients who clicked in the email.

  >[!NOTE]
  >
  >For more information on the difference between distinct people and targeted recipients, refer to [Targeted persons / recipients](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

This table of values shows the breakdown of deliveries, opens, clicks and raw reactivity per Internet domain. The following indicators are used:

* **[!UICONTROL Sent]**: Total number of messages sent on this domain. 
* **[!UICONTROL Complaints]**: Number of messages for this domain that have been reported as undesirable by the recipient. The rate is calculated based on the total number of messages sent on this domain.
* **[!UICONTROL Opens]**: Number of distinct targeted recipients for this domain who have opened a message at least once. The rate is calculated based on the total number of messages sent on this domain.
* **[!UICONTROL Clicks]**: Number of distinct targeted recipients who clicked in the same delivery at least once. The rate is calculated based on the total number of messages sent on this domain 
* **[!UICONTROL Raw reactivity]**: Percentage of the number of recipient who clicked in a delivery at least once compared to the number of recipients who opened a delivery at least once.

>[!NOTE]
>
>The domain names displayed in this report are defined in the itemized list used at cube level. To change, add or remove default domains, edit the **[!UICONTROL Domains]** itemized list and modify values and aliases. The **[!UICONTROL Others]** category includes domain names that don't belong to any value of the itemized list.
>
>Learn how to access and configure your enumerations in [this page](../config/enumerations.md).


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>The related percentages are calculated based on the number of messages forwarded successfully.

* **[!UICONTROL Distinct clicks for the population reached]**: Number of distinct people having clicked in a delivery at least once. 
* **[!UICONTROL Cumulated clicks]**: Total number of clicks by targeted recipients, excluding unsubscription links and mirror pages.
* **[!UICONTROL Recipient clicks]**: Number of distinct targeted recipients who clicked in the same delivery at least once.
* **[!UICONTROL Estimated recipient reactivity]**: Ratio of the number of recipients having clicked at least once in a delivery compared to the estimated number of recipients having opened a delivery at least once. Clicks on the opt-out and mirror page links are not taken into account.
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]**: Number of web pages visited following message reception.
* **[!UICONTROL Transactions]**: Number of purchases following message reception.
* **[!UICONTROL Total amount]**: Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]**: Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]**: Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]**: Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]**: Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]**: Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]**: Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]**: Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]**: This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]**: Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]**: Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## Delivery summary {#delivery-summary}

This report provides all the main information on the delivery. 

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

This section has two indicators:

* **[!UICONTROL Initial population]**: Total number of recipients targeted by the delivery. 
* **[!UICONTROL Messages rejected by the rule]**: Number of addresses ignored during the analysis when applying typology rules: address missing, quarantined, on denylist, etc. <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

The middle chart shows the breakdown per rule of messages rejected during the analysis.

**[!UICONTROL Delivery statistics]**

This section includes the following indicators:

* **[!UICONTROL Messages to be delivered]**: Total number of messages to be delivered after delivery analysis. 
* **[!UICONTROL Success]**: Number of messages processed successfully. The associated rate is the ratio with the number of messages to be delivered.
* **[!UICONTROL Errors]**: Total number of errors cumulated during deliveries and automatic rebound processing. The associated rate is the ratio with the number of messages to be delivered. 
* **[!UICONTROL New quarantines]**: Number of addresses quarantined following a failed delivery (user unknown, invalid domain). The associated rate is the ratio with the number of messages to be delivered.

## Hot clicks {#hot-clicks}

This report shows the message content (HTML and/or text) with, on each link, the percentage of clicks on links. Personalization blocks unsubscription links, mirror page links and offer links are taken into account in the total cumulated clicks but are not displayed in the report.

>[!NOTE]
>
>If your delivery contains offers (Interaction), a box appears in the part above the report displaying the percentage of clicks on the offers.


## Tracking statistics {#tracking-statistics}

This report provides statistics on opens, clicks and transactions.

It lets you track the marketing impact of the delivery. You can configure how values are displayed by changing the timescale (1-hour, 3-hour, or 24-hour view, etc.). Click **[!UICONTROL Refresh]** to confirm your selection.

This report provides a table of values and a Pareto chart which display the time required for the delivery to reach maximum efficiency. The following indicators are used:

* **[!UICONTROL Opens]**: Estimate of the time needed to reach a percentage of the total number of messages opened. Emails in text format aren't taken into account. [Learn more](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]**: Estimate of the time required to reach a percentage of the total number of clicks recorded. Clicks on the opt-out link and the mirror page are not taken into account.
<!--
* **[!UICONTROL Transactions]**: Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
--> 


## Cumulative reports {#cumulated-reports}

You can display cumulated reports on deliveries. To do this, select the deliveries to be compared to obtain the list of reports for these deliveries.

To select non-adjacent deliveries from the list, hold down the CTRL key while making your selection.

To select deliveries saved in a different folder click the **[!UICONTROL Display sub-levels]** icon, accessible in the toolbar. They will then be displayed in the same list.
