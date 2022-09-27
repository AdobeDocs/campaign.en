---
title: Work with Campaign and Adobe Experience Platform
description: Learn how to work with Campaign and Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
---
# Work with Campaign and Adobe Experience Platform

The Adobe Campaign Managed Cloud Service destination and source connectors allow seamless integration between Adobe Campaign and Adobe Experience Platform:

* Use **Adobe Campaign Managed Cloud Sources connector** to send Experience Platform segments over to Adobe Campaign for activation,

    ![](assets/aep-destination.png)

* Use **Adobe Campaign Managed Cloud Destination connector** to send Adobe Campaign delivery and tracking logs over to Adobe Experience Platform.

    ![](assets/aep-logs.png)

The steps to configure this integration in Adobe Experience Platform are as follows:

1. Configure a new Adobe Campaign Managed Cloud Services destination connection to activate a segment/audience and send that data over to Adobe Campaign.

    Provide details on the Campaign instance to use, select segments to activate for the destination then configure the attributes you want to export to Campaign.

    [Learn how to create an Adobe Campaign Managed Cloud Services destination connection](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configure a new Adobe Campaign Managed Cloud Services source connection to ingest Campaign events into Adobe Experient Platform.

    Provide details on the Campaign instance and the schema to use, select a dataset where data should be ingested, then configure the fields to retrieve.

    [Learn how to create an Adobe Campaign Managed Cloud Services source connection](https://www.adobe.com/go/sources-campaign-ui-en)
