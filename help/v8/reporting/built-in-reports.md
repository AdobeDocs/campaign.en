---
title: Adobe Campaign built-in reports
description: Built-in reports
feature: Reporting
role: User
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
---
# Adobe Campaign built-in reports {#ootb-reports}

This page provides the list of Adobe Campaign built-in reports, their content and their context. Adobe Campaign provides a range of built-in reports, accessible with the Client Console or an internet browser.

The following types of report are available:

* Reports on the entire platform. [Learn more](global-reports.md).
* Delivery reports. [Learn more](delivery-reports.md).

You can access built-in reports from the Campaign home page, the dedicated reports dashboard or the delivery list. The way the report displays in the UI depends on its context. 

A list of key reports is available on the home page and lets you access delivery data quickly. This list can be changed to suit your needs. You can also learn how to add your own reports to the **[!UICONTROL Reports]** tab. 

For more information about these custom configurations, refer to this [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html).


## Access built-in reports {#access-ootb-reports}

To access Campaign built-in reports:

1. Select the **[!UICONTROL Reports]** tab of the Adobe Campaign interface.

    ![](assets/reporting-access-from-home.png)

1. Use the search fields to filter the displayed reports.

1. Then click the report you want to display.

    ![](assets/edit-a-report.png)

1. Click the **[!UICONTROL Back]** link at the top of the screen takes you back to the list of reports.

    ![](assets/back-button.png)

Reports that are specific to a campaign or a delivery are accessible via their respective dashboards.

![](assets/reporting-on-delivery.png)

The principle is the same for lists, services, offers, etc. as shown below:

![](assets/reporting-on-offer.png)


## Reports on deliveries {#reports-on-deliveries}

The built-in reports provided by Adobe Campaign can be found in the table below.

For more on the content of these reports, refer to [this section](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> User activities (recipientActivity)<br /> </td> 
   <td> Breakdown of opens, clicks and transactions by time period.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery throughput (throughput)<br /> </td> 
   <td> Delivery throughput charts, in messages/hour and Mbits/s.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Failures and bounces (errors)<br /> </td> 
   <td> Bounces and non-deliverables by cause and domain.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking indicators (deliveryFeedback)<br /> </td> 
   <td> Summary of key indicators for tracking recipient behavior.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking indicators (mobileAppDeliveryFeedback)<br /> </td> 
   <td> Tracking indicators of a delivery to a mobile application.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Browsers (browserStatistics)<br /> </td> 
   <td> Statistics on browsers used by recipients who clicked in messages.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Sharing to social networks (deliveryForward)<br /> </td> 
   <td> Sharing activity and mail open statistics.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Hot clicks (hoturls)<br /> </td> 
   <td> Displays the message and the click rates superimposed.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Hypothesis report (deliveryHypothesis)<br /> </td> 
   <td> Displays the summary of measures on delivery hypotheses.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery statistics (statisticsPerDelivery)<br /> </td> 
   <td> Statistics (processed messages, delivered messages, hard bounces, soft bounces, clicks, unsubscriptions) per email domain.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Sharing activity statistics (forwardActivities)<br /> </td> 
   <td> Analysis of sharing activities, opens and subscriptions per time period.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking statistics (trackingStatistics)<br /> </td> 
   <td> Open, click and transaction rates report.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery summary (deliverySending)<br /> </td> 
   <td> Summary of delivery indicators: target, exclusion and messages sent.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery summary (deliveryStatistics)<br /> </td> 
   <td> Summary table for selected deliveries: Targets, Exclusions and Messages Sent.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Operating systems (osStatistics)<br /> </td> 
   <td> Statistics on the operating systems used by recipients who clicked in a message.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactivity rate (deliveryFeedbackSocial)<br /> </td> 
   <td> Delivery reactivity rate and reaction breakdown.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> URLs and click throughput (topUrlDelivery)<br /> </td> 
   <td> Most reactive URLs and associated click streams.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Reports on campaigns {#reports-on-campaigns}

Reports on campaigns concern the data in the **nms:operation** table.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> User activities (operationRecipientActivity)<br /> </td> 
   <td> Breakdown of opens, clicks and transactions by time period, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery throughput (operationThroughput)<br /> </td> 
   <td> Delivery throughput charts, in mails/hour and Mbits/s, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign expenses (budgetOperationExpenses)<br /> </td> 
   <td> Displays the campaign line items in detail, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Failures and bounces (operationErrors)<br /> </td> 
   <td> Bounces and non-deliverables by cause and domain, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring cost lines (budgetExplorerOperation)<br /> </td> 
   <td> Descriptive analysis of cost lines, depends on MRM.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking indicators (operationFeedback)<br /> </td> 
   <td> Overview of key tracking indicators: Opens, Clicks and Transactions, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sharing to social networks (operationForward)<br /> </td> 
   <td> Sharing activity and mail open statistics, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hypothesis report (operationHypothesis)<br /> </td> 
   <td> Displays the summary of hypothesis measurements for the campaign deliveries, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sharing activity statistics (forwardActivityOpt)<br /> </td> 
   <td> Analysis of sharing activities, opens and subscriptions per time period, depends on Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery summary (operationStatistics)<br /> </td> 
   <td> Summary chart of the campaign deliveries: Targets, Exclusions and Messages Sent.<br /> </td> 
  </tr> 
  <tr> 
   <td> URLs and click throughput (operationTopUrlDelivery)<br /> </td> 
   <td> Most reactive URLs and associated click streams, depends on Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Reports on services {#reports-on-services}

Reports on services concern the data in the **nms:service** table.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Fan acquisitions (socialAcquisitionsByWebapp)<br /> </td> 
   <td> Which web applications enabled the prospect acquisitions? Depends on Social marketing add-on.<br /> </td> 
  </tr> 
  <tr> 
   <td> Breakdown of subscriptions (mobileAppDistribution)<br /> </td> 
   <td> Breakdown of active subscriptions per mobile application, depends on Mobile app channel add-on.<br /> </td> 
  </tr> 
  <tr> 
   <td> Subscription tracking (subscriptionsProgress)<br /> </td> 
   <td> Evolution of the subscriptions to information services<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactivity rate (socialReactionRate)<br /> </td> 
   <td> What are the reactivity rates for the latest deliveries? Depends on Social marketing add-on.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reactivity rate (mobileAppReactivityRate)<br /> </td> 
   <td> Reactivity rate for the latest deliveries, depends on Mobile app channel add-on.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Budget reports {#budget-reports}

The built-in reports provided by Adobe Campaign can be found in the table below.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Costs linked to the program(s) (budgetProgramCost)<br /> </td> 
   <td> Breakdown of program costs.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Budget evolution (budgetEvolution)<br /> </td> 
   <td> Evolution of budget costs by commitment level.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Cumulative evolution of the budget (budgetCumulativeEvolution)<br /> </td> 
   <td> Evolution of the cumulated budget costs broken down by commi<br /> tment level. </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring cost lines (budgetExplorerBudget)<br /> </td> 
   <td> Descriptive analysis of cost lines.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring cost lines (budgetExplorer)<br /> </td> 
   <td> Descriptive analysis of cost lines.<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring cost lines (budgetExplorerPlan)<br /> </td> 
   <td> Descriptive analysis of cost lines.<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring cost lines (budgetExplorerProgram)<br /> </td> 
   <td> Descriptive analysis of cost lines.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Summary of the budget(s) (budget)<br /> </td> 
   <td> Snapshot of the main costs, expense categories and budgets.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Reports on simulations {#reports-on-simulations}

Reports on simulations concern the data in the **nms:simulation** table.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Detail of simulation exclusions (dlvSimuLossesDetail)<br /> </td> 
   <td> Detailed table of all causes of exclusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Breakdown of offers by rank (offerSimulationRanking)<br /> </td> 
   <td> Breakdown of offers in the simulation, by rank.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simulation summary (dlvSimuLossesSummary)<br /> </td> 
   <td> Summary of simulation volumes and exclusions.<br /> </td> 
  </tr> 
  <tr> 
   <td> Overlap statistics (dlvSimuOverlapping)<br /> </td> 
   <td> Delivery target overlap volumes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Summary of exclusions due to the simulation (dlvSimuLossesSimu)<br /> </td> 
   <td> Table of exclusions due to the simulation.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Reports on Web applications {#reports-on-web-applications}

Reports on Web applications concern the data in the **nms:WebApp** table.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Documentation (surveyDictionary)<br /> </td> 
   <td> Description of survey structure, depends on the Survey Manager add-on.<br /> </td> 
  </tr> 
  <tr> 
   <td> Main (surveyProperties)<br /> </td> 
   <td> Survey properties<br /> </td> 
  </tr> 
  <tr> 
   <td> Breakdown of responses (surveyDistribution)<br /> </td> 
   <td> Breakdown of responses to questions.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Other ootb reports {#other-ootb-reports}

The following reports are also provided built-in. For more on this, refer to the document on functionality which they concern.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label and Internal name</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schema</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Offer analysis (offerAnalysis)<br /> </td> 
   <td> Offer analysis per date and channel, depends on the Interaction add-on.<br /> </td> 
   <td> nms:offer<br /> </td> 
  </tr> 
  <tr> 
   <td> Re-marketing efficiency (remarketingEffect)<br /> </td> 
   <td> Measurement of re-marketing efficiency<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> History of social prospect acquisitions (socialVisitorStatistics)<br /> </td> 
   <td> History of Twitter and Facebook prospect acquisitions, depends on the Social marketing add-on.<br /> </td> 
   <td> nms:visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> Recent proposition tracking (recentPropositions)<br /> </td> 
   <td> Real-time proposition tracking<br /> </td> 
   <td> nms:propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
