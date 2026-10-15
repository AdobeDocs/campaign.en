---
title: Grant permissions to Campaign v8
description: Learn how to grant permissions to Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
---
# Get started with permissions

In Adobe Campaign, users are **operators** and **operator groups** represent user roles.

An operator is an Adobe Campaign user who has permissions to log in and perform actions. By default, operators are stored in the **[!UICONTROL Administration > Access management > Operators]** node.

Adobe Campaign comes with built-in operator groups such as Campaign Managers or Workflow Supervisors. Learn more about permissions in [this section](../start/gs-permissions.md)

As a member of an operator group, a user has rights to perform operations, called 'Named Rights', and has access to data, which is contained in folders in the **Explorer** view. An operator can be a member of multiple operator groups: rights and access permissions are additive.

Named Rights grant permissions to:

* Perform operations
    For example, the **Analyze** button in the Delivery editor is activated for members of the **Delivery Operator** group who have the **Prepare Delivery** Named Right

* Access to folders
    Membership of Operator Groups can grant or restrict access rights to folders, by changing the security settings on folders. Learn more in [this page](../start/folder-permissions.md). For example it can impact: **Write access** to create new entities (such as deliveries, profiles, etc.), **Read access** to use entities, **Delete access** to delete entities.

## Security zones

Each operator needs to be linked to a zone to log on to an instance and the operator IP must be included in the addresses or address sets defined in the security zone. Security zone configuration is carried out in the configuration file of the Adobe Campaign server.

Operators are linked to a security zone from its profile in the console, accessible in the **[!UICONTROL Administration > Access management > Operators]** node.

>[!NOTE]
>
>As a Managed Cloud Services user, Adobe sets the security zones for you. For more information, [contact Adobe](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Learn more**

* [Built-in Named Rights](../start/gs-permissions.md)

* [Steps to set up permissions](../start/manage-permissions.md)
