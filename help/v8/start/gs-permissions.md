---
title: Get started with permissions in Campaign v8
description: Learn steps to define permissions in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
---
# Get started with permissions{#gs-permissions}

Adobe Campaign lets you define and manage the rights assigned to users. These are a set of rights and restrictions that authorize or deny:

* Access to certain capabilities
* Access to certain data
* Access to certain actions (create, modify, delete)

These permissions are defined by combining operator group permissions, named rights and permissions on folders.

In Adobe Campaign, users are **operators** and **operator groups** represent user roles. An operator is an Adobe Campaign user who has permissions to log in and perform actions. Users are created in the Admin Console. The permissions apply to user profiles or groups of users. There are two types of permissions you can grant:

* You can define groups of operators to which you attribute rights, then associate the operators with one or more groups. This enables you to reuse rights and make operator profiles more consistent. It also facilitates the management and maintenance of user profiles. 
* You can assign named rights directly to users, in some cases to overload the rights allocated via groups.

## Key steps to grant permissions{#key-steps-permissions}

As a product administrator, you can grant permissions to the users of your organization. Permissions are granted through Adobe Admin Console and Campaign client console. Users log on to Adobe Campaign with their Adobe ID. Learn how to connect to Adobe Campaign in [this page](connect.md).

Key steps are:

* **Step 1**: Define your operator groups and assign them permissions in Campaign client console. [Learn more](manage-permissions.md#create-product-profile).
    Note that you can also use built-in operator groups to start with. These default groups, and their permissions, are listed in [this section](manage-permissions.md#ootb-productprofiles).
* **Step 2**: Create product profiles in Adobe Admin Console which match with those groups. [Learn more](manage-permissions.md#create-product-profile).
    You can use built-in product profiles to start with. [Learn more](manage-permissions.md#ootb-productprofiles).
* **Step 3**: Create users in Adobe Admin Console, and assign them to a product profile. [Learn more](manage-permissions.md#add-users).
* **Step 4** (optional): Assign permissions on folders. [Learn more](manage-permissions.md#ootb-productprofiles).

## About the Admin Console{#gs-admin-console}

The Adobe Admin Console is a central location for managing the Adobe entitlements across your organization. It is accessible to product administrators only.

Use the Admin Console to add users, create and assign product profiles (which are groups of operator roles).

Learn how to add users in [this page](manage-permissions.md#add-users).

## About product profiles{#ootb-product-profiles}

Product profiles are groups of products and services that you can assign to users. In Adobe Experience Cloud, permissions are based on a product's profile, not on the user. However, you can delegate administrative rights to specific users.

In the Admin Console, each Adobe Experience Cloud **product profile** for Campaign is associated to an **operator group** in Campaign client console.

Learn how to create and assign product profiles in [this page](manage-permissions.md#create-a-product-profile).

## Campaign named rights{#named-rights}

As a member of a product profile (i.e operator group), a user has rights to perform operations, called 'Named Rights', and has read and/or write access to data. An operator can be a member of multiple operator groups: rights and access permissions are additive.

Learn more about named rights in [this section](manage-permissions.md#use-named-rights).
