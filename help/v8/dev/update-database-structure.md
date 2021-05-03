---
solution: Campaign Classic
product: campaign
title: Update the database structure
description: Update the database structure
---
# Update the database structure{#updating-the-database-structure}

To apply the modifications made to the schemas, launch the Database update assistant. This assistant is accessible via **[!UICONTROL Tools > Advanced > Update database structure]** . It checks whether the physical structure of the database matches its logical description and executes the SQL update scripts.

![](assets/schema_update.png)

The modules in the database are automatically populated and activated.

![](assets/schema_update_select.png)

The **[!UICONTROL Add stored procedures]** and **[!UICONTROL Import initialization data]** options are used to launch the initial SQL scripts and the data packages executed when the database is created.

You can import a set of data from an external data package. To do this, select **[!UICONTROL Import a package]** and enter the XML file of the package.

Follow the steps and view the database update SQL script:

![](assets/schema_update2.png)

>[!NOTE]
>
>This is in an editing field and can be modified in order to delete or add SQL code.

Next, launch the database update:

![](assets/schema_update3.png)
