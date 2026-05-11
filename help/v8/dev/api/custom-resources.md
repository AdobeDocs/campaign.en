---
title: Custom resources
description: Learn more about custom resources management with APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
TQID: https://experienceleague.adobe.com/T-CLyTlNyyuckhraPX-rAU7TOrMfMbcZdrDcneiflg0
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
# Custom resources {#custom-resources}

Adobe Campaign comes with a pre-defined data model, where data is defined through different resources. You can enrich the data model that is provided by extending the resources to add your own custom fields or custom tables, such as purchase or product tables.

Custom resources are accessible through APIs using the **/profileAndServicesExt** endpoint, and the custom resource name.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>For resources that are not out-of-the-box, always use the <b>"cus"</b> prefix before the resource's name.

You can perform any operation with custom resources, as long as they are linked to the Profile table. For example, let's consider the tables structure below:

![alt text](assets/cusresources.png)

In that case, all resources from the **Transaction**, **TransactionDetails** and **Product** tables are available as long as they are linked to the **Profile** table.

<br/>

***Sample request***

Sample GET request to access the extended profileAndServicesExt resource.

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \

```

It returns the list of all linked custom resources. You can then use the resources URLs to perform any API task described in this documentation.

```

{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}

```
