---
solution: Campaign v8
product: Adobe Campaign
title: Work with Campaign and Adobe Analytics
description: Learn how to work with Campaign and Adobe Analytics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
---
# Work with Campaign and Adobe Analytics

## Experience Cloud Triggers

You can use Experience Cloud Triggers to connect data between Adobe Campaign and Adobe Analytics using the pipeline. The pipeline retrieves user's actions or triggers from your website. A cart abandonment is an example of trigger. Triggers are processed in Adobe Campaign to send emails in near real time.

:speech_balloon: As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to implement Experience Cloud triggers with Campaign.

## Adobe Analytics Data Connector

TO UPDATE WITH THE NEW INTEGRATION

You can also configure Adobe Analytics Data Connectors to integrate Campaign and Analytics.

Data Connector (previously known as Adobe Genesis) allows Adobe Campaign and Adobe Analytics to interact through the **Web Analytics connectors** package. This integration shares data from Analytics to Campaign as segments related to user behavior following an email. Conversely, it sends indicators and attributes of email campaigns delivered by Adobe Campaign to Adobe Analytics - Data connector.

Thanks to these integrations, Adobe Campaign can recover data on visitor behavior for one or more sites following a marketing campaign, and (after analysis) run re-marketing campaigns with a view to converting them into buyers. Conversely, the Web analytics tools enable Adobe Campaign to forward indicators and campaign attributes to their platforms.

The action fields for each tool are as follows:

* Adobe Analytics:

    * marks the email campaigns launched with Adobe Campaign
    * saves recipient behavior, on the site they browsed after clicking the campaign email, in the form of segments. Segments are related to abandoned products (viewed but not added to the cart or purchased), purchases or cart abandonments.

* Adobe Campaign:

    * sends the indicators and campaign attributes to the connector, which in turn forwards them to the Web analytics tool
    * recovers and analyzes segments
    * triggers a re-marketing campaign

Learn more about Adobe Campaign and Adobe Analytics in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes)

:speech_balloon: As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Analytics Data Connector with Campaign.

