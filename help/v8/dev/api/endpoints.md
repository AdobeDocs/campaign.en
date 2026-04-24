---
title: Endpoints
description: Learn more about the APIs endpoints.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Endpoints {#endpoints}

The available endpoints for Adobe Campaign REST API:

* **/profileAndServices**: interact with out of the box fields. Extended fields are not accessible with this endpoint.
* **/profileAndServicesExt**: interact with custom fields added during Profile or Services custom resource extension. For more on custom resources, refer to [this section](custom-resources.md).
* **/&lt;transactionalAPI&gt;**: interact with the transactional messages API (the name of the transactional messages API endpoint depends on your instance configuration). For more on this, refer to [this section](managing-transactional-messages.md).
* **/workflow/execution**: interact with workflows. For more on this, refer to [this section](controlling-a-workflow.md).

By default, the main resources available for the **profileAndServices** and **profileAndServicesExt** APIs are:

* **/profile**: interact with profiles from Campaign database. To add profiles to a service, use the **/service** endpoint. For more on profiles in Campaign, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: manage subscription services. For more on services in Campaign, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>All other resources that have been extended or created are available via the **ProfileAndServicesExt** API only. They must be linked to the **Profile** resource in order to be accessible.
