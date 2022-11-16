---
title: Get started with permissions in Campaign v8
description: Learn how to define permissions in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
---
# Get started with permissions{#gs-permissions}

In Adobe Campaign, users are **operators** and **operator groups** represent user roles.

An operator is an Adobe Campaign user who has permissions to log in and perform actions. By default, operators are stored in the **[!UICONTROL Administration > Access management > Operators]** node.

As a Campaign v8 user, you connect to Adobe Campaign with your Adobe ID.

As a product administrator, you can grant permissions to the users of your organization.  Permissions are granted through the Adobe Admin Console and Campaign Client Console. 

## About the Admin Console{#gs-admin-console}

The Adobe Admin Console is a central location for managing the Adobe entitlements across your organization. It is accessible to product administrators only.

Use the Admin Console to add users, create and assign product profiles (which are groups of operator roles).

Learn how to add users in [this page](manage-permissions.md#add-users).

## Built-in product profiles{#ootb-product-profiles}

Product Profiles are groups of products and services that you can assign to users. In Adobe Experience Cloud, permissions are based on a product’s profile, not on the user. However, you can delegate administrative rights to specific users.

In the Admin Console, each Adobe Experience Cloud product profiles for Campaign is associated to an operator group in Campaign UI.


Learn how to create and assign product profiles in [this page](manage-permissions.md#create-a-product-profile).

## Named rights{#named-rights}

As a member of a product profile (i.e operator group), a user has rights to perform operations, called 'Named Rights', and has read and/or write access to data. An operator can be a member of multiple operator groups: rights and access permissions are additive.



<!--
## Security zones

Each operator needs to be linked to a zone to log on to an instance and the operator IP must be included in the addresses or address sets defined in the security zone. Security zone configuration is carried out in the configuration file of the Adobe Campaign server.

Operators are linked to a security zone from its profile in the console, accessible in the **[!UICONTROL Administration > Access management > Operators]** node.

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, Adobe sets the security zones for you. For more information, [contact Adobe](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

-->

**Learn more in Campaign Classic v7 documentation**

* [Built-in Named Rights](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target="_blank"}

* [Built-in Operator Groups](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target="_blank"}

* [Steps to set up permissions](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target="_blank"}
