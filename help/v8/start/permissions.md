---
solution: Campaign
product: Adobe Campaign
title: Grant permissions to Campaign v8
description: Learn how to grant permissions to Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
---
# Get started with permissions

In Adobe Campaign, users are **operators** and **operator groups** represent user roles.

An operator is an Adobe Campaign user who has permissions to log in and perform actions. By default, operators are stored in the **[!UICONTROL Administration > Access management > Operators]** node.

Adobe Campaign comes with built-in operator groups such as Campaign Managers or Workflow Supervisors. All built-in groups are listed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target="_blank"}.

As a member of an operator group, a user has rights to perform operations, called 'Named Rights', and has access to data, which is contained in folders in the **Explorer** view. An operator can be a member of multiple operator groups: rights and access permissions are additive.

Named Rights grant permissions to:

* Perform operations
    For example, the **Analyze** button in the Delivery editor is activated for members of the **Delivery Operator** group who have the **Prepare Delivery** Named Right

* Access to folders
    Membership of Operator Groups can grant or restrict access rights to folders, by changing the security settings on folders. [Learn more in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target="_blank"}. For example it can impact: **Write access** to create new entities (such as deliveries, profiles, etc.), **Read access** to use entities, **Delete access** to delete entities.

## Security zones

Each operator needs to be linked to a zone to log on to an instance and the operator IP must be included in the addresses or address sets defined in the security zone. Security zone configuration is carried out in the configuration file of the Adobe Campaign server.

Operators are linked to a security zone from its profile in the console, accessible in the **[!UICONTROL Administration > Access management > Operators]** node.

💬 As a Managed Cloud Services user, Adobe sets the security zones for you. For more information, [contact Adobe](support.md#support).

**Learn more in Campaign Classic v7 documentation**

* [Built-in Named Rights](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target="_blank"}

* [Built-in Operator Groups](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target="_blank"}

* [Steps to set up permissions](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target="_blank"}
