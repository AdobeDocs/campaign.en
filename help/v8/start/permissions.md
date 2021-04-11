---
solution: Campaign Classic
product: campaign
title: Grant permissions to Campaign v8
description: Learn how to grant permissions to Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917,ed68cb7f-da6a-470c-bcd2-e07660f48b17
---

# Get started with permissions

In Adobe Campaign, users are **operators** and **operator groups** represent user roles.

Adobe Campaign comes with built-in operator groups such as Campaign Managers or Workflow Supervisors. All built-in groups are listed in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

As a member of an operator group, a user has rights to perform operations, called 'Named Rights', and has access to data, which is contained in folders in the **Explorer** view. An operator can be a member of multiple operator groups: rights and access permissions are additive.

Named Rights grant permissions to:

* Perform operations
    For example, the **Analyze** button in the Delivery editor is activated for members of the **Delivery Operator** group who have the **Prepare Delivery** Named Right

* Access to folders
    Membership of Operator Groups can grant or restrict access rights to folders, by changing the [security settings on folders](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder). For example it can impact: **Write access** to create new entities (such as deliveries, profiles, etc.), **Read access** to use entities, **Delete access** to delete entities.

**Learn more**

* [Built-in Named Rights](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

* [Built-in Operator Groups](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

* [Steps to set up permissions](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)
