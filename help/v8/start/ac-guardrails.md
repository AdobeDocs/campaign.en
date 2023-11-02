---
title: Campaign v8 guardrails
description: Campaign v8 guardrails
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
---
# Product guardrails{#guardrails}

Entitlements, product limitations and performance guardrails are listed in [Adobe Campaign Managed Cloud Services product description page](https://helpx.adobe.com/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

You will find below additional guardrails and limitations when using [!DNL Adobe Campaign]. 

Guardrails and limitations identify capabilities, architecture, or processes that are not supported by this release of the product, or that do not interoperate correctly with it. Review these limitations carefully.

* Adobe Campaign v8 is not available for on-premise/hybrid deployments - only released as an Adobe Managed Cloud Service
* No automatic migration to Adobe Campaign v8 is available for existing customers
* In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), no bi-directional data replication is provided: replication happens only from the Campaign local database to the Cloud database
* Capabilities listed [in this section](v7-to-v8.md#gs-unavailable-features) are not available in the current Campaign v8 build
* Some non-available or removed features are still visible in the user interface
* In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), subscription (opt-in) and unsubscription (opt-out) mechanisms, and Mobile registration are asynchronous processes. Requests are processed each hour through a specific technical workflow. [Learn more](../architecture/replication.md#tech-wf)
* In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), duplicates need to be handled manually by end-users. [Learn more](../architecture/keys.md)
* Adobe Campaign v8 does not support extended throughput on API and web applications - in case of specific needs, contact Adobe to get guidance
* In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), Adobe Campaign Campaign Optimization module does not take into account scheduled deliveries in pressure typology rules. Learn more in [this page](../../automation/campaign-opt/pressure-rules.md)