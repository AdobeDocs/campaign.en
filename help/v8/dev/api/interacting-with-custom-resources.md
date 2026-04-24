---
title: Interacting with custom resources
description: Learn more about custom resources management with APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
TQID: https://experienceleague.adobe.com/w8FCKOzUXzquVrDL2R6BJkkKWN-S1BaXZ4-sKl93iRI
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Interacting with custom resources {#interacting-with-custom-resources}

The **/customResources** endpoint allows you to expose the Campaign custom resources in REST. Based on this API, an integration between custom entities and external endpoints is available.

The /customResources endpoint has exactly the same behavior as /profileAndServices endpoint.

The custom resources that are exposed within this API are:

* all the entities that are not exposed under /profileAndServicesExt 
* all the entities that are not linked to profile and, for these entities, their children and grandchildren.
* by default, all entities that are not linked to anything, and their children and grandchildren.

>[!NOTE]
>The custom resources that are available under /profileAndServicesExt are not exposed in the /customResources API.


Here is an example to retrieve the metadata from a custom resource:

```
GET /customResources/resourceType/<customResourceName>
```

To perform a creation, update or deletion, the GET, POST, PATCH, DELETE are used.

```
POST /customResources/<customResourceName>
```
