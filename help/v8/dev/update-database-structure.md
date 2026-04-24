---
title: Update the database structure
description: Update the database structure
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Update the database structure {#updating-the-database-structure}

To apply the modifications made to the schemas, launch the Database update wizard. This assistant is accessible via **[!UICONTROL Tools > Advanced > Update database structure]**. It checks whether the physical structure of the database matches its logical description and executes the SQL update scripts.

![](assets/schema_update.png)

The modules in the database are automatically populated and activated.

![](assets/schema_update_select2.png)

Follow the steps and view the database update SQL script:

![](assets/schema_update2.png)

>[!NOTE]
>
>This is in an editing field and can be modified in order to delete or add SQL code.

Next, launch the database update:

![](assets/schema_update3.png)
