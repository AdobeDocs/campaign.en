---
title: Data model concepts
description: Learn about the Adobe Campaign data model and how to modify it.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
---

# Data model concepts{#data-model-concepts}

>[!CAUTION]
>
>Creating and modifying resources are sensitive operations which must be performed by expert users only.

The **[!UICONTROL Administration]** > **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

The data used by Adobe Campaign is defined through different resources. You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

Built-in resources (such as campaigns, emails, or audiences) cannot be modified. However, custom resources can be extended to add new fields.

Extension fields are generated with a prefix so that they never conflict with the built-in fields.

All workflow activities are listed in [this section](../../developing/using/get-started-data-model.md), including use cases and samples.
