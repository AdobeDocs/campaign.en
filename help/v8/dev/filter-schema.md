---
title: Filter Campaign schemas
description: Learn how to filter Campaign schemas
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
TQID: https://experienceleague.adobe.com/2T0OxjyVTM9-lzsOfcaqv81YVtVvrNpprpyC0VLoWgU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Filter schemas{#filter-schemas}

## System filters {#system-filters}

You can filter schema access to specific users, depending on their permissions. System filters let you manage the read and write permissions of entities detailed in schemas, using **readAccess** and **writeAccess** parameters.

>[!NOTE]
>
>This restriction applies only to non technical users: a technical user, with related permissions, or using a workflow, will be able to retrieve and update data.

* **readAccess**: provides read only access to schema data.

  **Warning** - All linked tables must be set with the same restriction. This configuration can impact performances.

* **writeAccess**: provides write access to schema data.

These filters are entered at the main **element** level of the schemas and, as shown in the following examples, can be formed to restrict access.

* Restrict WRITE permissions

  Here, the filter is used to disallow WRITE permissions on the schema for operators without the ADMINISTRATION permission. This means that only administrators will have write permissions on entities described by this schema.

  ```
  
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Restrict READ and WRITE permissions:

  Here, the filter is used to disallow both READ and WRITE permissions on the schema for all operators. Only the **internal** account, represented by the expression "$(loginId)!=0", has these permissions.

  ```
  
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Possible **expr** attribute values used to define the condition are TRUE or FALSE.

>[!NOTE]
>
>If no filter is specified, all operators will have read and write permissions to the schema.

## Protect built-in schemas

By default, built-in schemas are only accessible with WRITE permissions for operators with ADMINISTRATION rights:

* ncm:publishing
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>READ and WRITE permissions for the **xtk:sessionInfo** schema are only accessible by the internal account of an Adobe Campaign instance.

## Modify system filters of built-in schemas

Built-in schemas are protected to avoid compatibility issues with older versions. Adobe recommends you not to modify the default schema parameters to guarantee optimal security. 

However, in specific contexts, you may need to modify the system filters of the built-in schemas. To perform this, follow the steps below:

1. Create an extension for the built-in schema or open an existing extension.
1. Add a child element **`<sysfilter name="<filter name>" _operation="delete"/>`** in the main element to ignore the filter under the same in the built-in schema.
1. You can add a new filter, as detailed in the [System filters](#system-filters) section.
