---
title: Migration of technical users to Adobe Developer console
description: Learn how to migrate user access management from Campaign Standard to Campaign V8
feature: Technote
role: Admin
---
# User access management from Campaign Standard to Campaign V8 {#user-management-acs}

Both Adobe Campaign Standard and Adobe Campaign V8 enable users to define and manage permissions for different users/operators. These permissions consist of specific rights that grant users access to various features of the product. However, the two products use distinct approaches and implementations for managing user access.

The following concepts are used in Adobe Campaign Standard and Campaign V8 to achieve user access management:

|Campaign Standard| Campaign V8 |
|---------|----------|
| User | Operator |
| Role | Named Right |
| Security Group | Operator Group |
| Organizational unit | Folder Permission |

## Migration Approach from Security group to Operator group

>[!CAUTION]
>
>The capabilities of these Roles/Named rights may vary in implementation, potentially causing authorization issues (e.g., privilege elevation or functionality disruptions). We recommend users to review these mappings after the transition to ensure proper access control. [Learn more on permissions](../../v8/start/manage-permissions.md)

The table below outlines the migration approach for user role groups when transitioning from Adobe Campaign Standard to Campaign V8. In Campaign Standard, a **Security group**, referred to as an **Operator group** in Campaign V8, is used to assign a set of roles to a user. While some security groups/operator groups are available out-of-the-box, users can create new groups or modify existing ones if needed.

| | **Campaign Standard**| **Campaign V8** |
|---------|----------|---------|
| **Terminology** | Security Group | Operator Group |

In both Adobe Campaign Standard and Campaign V8, **Security groups** and **Operator groups** are mapped to Product profiles in the Admin console. If you want to assign a **Security group** or **Operator group** to a user, you can link the corresponding **Product profile** in the Admin console. This association is synchronized when the user logs in. [Learn more on Product profile](../../v8/start/manage-permissions.md)

| **Campaign Standard Security group** | **Campaign V8 Operator group** |
|----------|---------|
| Administrators | Administrators |
| Delivery supervisors | Administrators |
| Workflow supervisors | Workflow supervisors |

## Migration approach from User roles to Named rights

In Adobe Campaign Standard, the term **User role** is referred to as **Named right** in Campaign V8. The table below outlines the terminology used for **Named rights** in Campaign V8 corresponding to **User roles** in Campaign Standard.

| **Campaign Standard User role** | **Campaign V8 Named right** | **Description** |
|----------|---------|---------|
| Administration | Administration | User with the Administration right has full access to the instance.|
| Data Model  | Administration | Right to run publications and create custom resources. Schema creation related functionality available to Admin in Campaign V8. |
| Deliverability | Administration | Right to approve previously analyzed deliveries. |
| Export | Export | Right to export data. |
| File Access | Files Access | Right to approve previously analyzed deliveries. |
| Generic import  | Import | Right for generic data import |
| Prepare deliveries | Prepare deliveries | Right to create, modify, prepare and delete deliveries. |
| SQL Script Execution | SQL Script Execution | Right to execute any SQL command directly on the database. |
| Start deliveries | Start deliveries | Right to approve previously analyzed deliveries. |
| System Command Execution | Program Execution | Right to execute system commands on the server.|
| Workflow | Workflow | Right to manage the execution of workflows start, stop, pause etc. |

## Migration approach from Organizational unit

In Adobe Campaign Standard, the **Organization uni**t is mapped to the existing **Folder** hierarchy model in Campaign V8 to maintain similar access control. [Learn more on folder management](../../v8/start/folder-permissions.md)

| | **Campaign Standard**| **Campaign V8** |
|---------|----------|---------|
| **Terminology** | Organizational unit | Folder | 

## Migration approach from Program 

In Campaign V8, **Programs** are represented as **Folders**. Campaign V8 enables the creation of folders and allows restricting access to them.

By using **Groups** and **Named rights**, **Operators** can be granted access to specific **Folders** within the navigation hierarchy, with the ability to assign read, write, and delete permissions. [Learn more on folder management](../../v8/start/folder-permissions.md)

Since a **Program** is treated as a **Folder** in Campaign V8, its access can be managed in the same way as any other folder. After migration, Campaign Standard administrators can follow these steps:

1. From the explorer, right-click on any folder and select **[!UICONTROL Properties...]**.
1. Navigate to the **[!UICONTROL Security]** tab.
1. Modify the operator group permissions as per the desired access model.  

## Product profile mapping to access REST APIs  

To access transactional APIs from the execution instance in Campaign V8, a new **Product profile** is required, in addition to the **Administrator** and **Message Center** product profiles. This new **Product profile** will be added to existing or pre-created technical accounts in Campaign Standard.

After migration, Campaign Standard users should review their **Product Profile mappings** and assign the appropriate **Product Profile** if they do not wish to link their **Technical accounts** to the **Administrator** Product Profile. For future integrations, we recommend using the Campaign V8 **Tenant ID** in the **REST URL** instead of the previous Campaign Standard **Tenant ID**.

## Migration of access to built-in Campaign resources for Campaign Standard operators

Operators migrated from Campaign Standard will have read access to specific built-in resources in Campaign V8.

## Non-migrated security groups and roles {#non-migrated-groups-roles}

Below is a list of Campaign Standard roles that have not been transitioned:

* Default Relay Account  

* Message Center Push  
 
Below is a list of Campaign Standard security group mappings that have not been transitioned.
 
* Message Center Agents

* Message Center Push Agents

* Adobe Experience Manager application managers   

* Relay Account
  
 

  

  

 