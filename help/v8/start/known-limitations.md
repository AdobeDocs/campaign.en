---
title: Campaign v8 known limitations
description: Known limitations
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: yes
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
---
# Known limitations

Known limitations identify capabilities, architecture, or processes that are not supported by this release of the product, or that do not interoperate correctly with it. Review these limitations carefully.

For Adobe Campaign v8, the following limitations exist:

* Adobe Campaign v8 is not available for on-premise/hybrid deployments - only released as an Adobe Managed Cloud Service.
* Existing customers cannot migrate from an existing Adobe Campaign environment to Adobe Campaign v8
* No bi-directional data replication: replication happens only from the Campaign local database to the Cloud database
* Capabilities listed [in this section](capability-matrix.md#gs-unavailable-features) are not available in the current Campaign v8 build
* Some non-available or removed features are still visible in the user interface
* Subscription (opt-in) and unsubscription (opt-out) mechanisms, and Mobile registration are asynchronous processes. Requests are processed each hour through a specific technical workflow. [Learn more](../config/replication.md#tech-wf)
* Duplicates need to be handled manually by end-users. [Learn more](../dev/keys.md)
* Adobe Campaign v8 does not support extended throughput on API and web applications. In case of specific needs, contact Adobe to get guidance.
* Adobe Campaign Campaign optimization module does not take into account scheduled deliveries in pressure typology rules. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=en#setting-the-period).