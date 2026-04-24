---
title: Extend Campaign schemas
description: Learn how to extend Campaign schemas
feature: Schema Extension, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
TQID: https://experienceleague.adobe.com/KxMO1S6yuFZUJAUIeSaF-J-s-SBLoODGWcOxImPONg0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Extend a schema{#extend-schemas}

As a technical user, you can customize Campaign datamodel to meet the needs of your implementation: add elements to an existing schema, modify an element in a schema or delete elements.

Key steps to customize Campaign datamodel are:

1. Create an extension schema
1. Update Campaign database
1. Adapt the input form

>[!CAUTION]
>Built-in schema must not be modified directly. If you need to adapt a built-in schema, you must extend it.

For a better understanding of Campaign built-in tables and their interaction, refer to [this page](datamodel.md). See also recommendations when creating a new schema in [this page](create-schema.md).

To extend a schema, follow the steps below:

1. Navigate to the **[!UICONTROL Administration > Configuration > Data schemas]** folder in the Explorer.
1. Click the **New** button and select **[!UICONTROL Extend the data in a table using an extension schema]**.

    ![](assets/extend-schema-option.png)

1. Identify the built-in schema to extend and select it.

    ![](assets/extend-schema-select.png)

    By convention, name the extension schema the same as the built-in schema, and use a custom namespace.  Note that some namespaces are internal only. [Learn more](schemas.md#reserved-namespaces)

    ![](assets/extend-schema-validate.png)

1. Once in the schema editor, add the elements you need using the contextual menu, and save.

    ![](assets/extend-schema-edit.png)

    In the example below, we add the **MembershipYear** attribute, put a length limit for last name (this limit will overwrite the default one), and remove the birth date from the built-in schema.

    ![](assets/extend-schema-sample.png)

    ```
    <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
            img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
            mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
     <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
        <attribute label="Member since" name="MembershipYear" type="long"/>
        <attribute length="50" name="lastName"/>
        <attribute _operation="delete" name="birthDate"/>
    </element>
    </srcSchema>
    ```

1. Disconnect and reconnect to Campaign to check schema structure update in the **[!UICONTROL Structure]** tab.

    ![](assets/extend-schema-structure.png)

1. Update the database structure to apply your changes. [Learn more](update-database-structure.md)

1. Once changes are implemented in the database, you can adapt the recipient input form to make your changes visible. [Learn more](forms.md)
