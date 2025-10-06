---
title: Campaign interface settings
description: Learn how to customize Campaign interface settings
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
---
# Campaign user interface settings {#ui-settings}

## Default units {#default-units}

In Adobe Campaign, for fields which express a duration (e.g. validity period of the resources, approval deadline for a task, etc.), values can be expressed in the following **units**:

* **[!UICONTROL s]** for seconds
* **[!UICONTROL mn]** for minutes
* **[!UICONTROL h]** for hours
* **[!UICONTROL d]** for days

## Customize Campaign Explorer{#customize-explorer}

You can add folders to Campaign Explorer, create views and assign permissions.

Learn how to manage folders and views in [this page](../audiences/folders-and-views.md)

## Manage and customize lists {#customize-lists}

In Campaign Client Console, data is displayed in lists. You can adapt these lists to your needs. For example, you can add columns, filter data, count records, save and share your settings.

In addition, you can create and save filters.  Learn more about filters in [this page](../audiences/create-filters.md).

### Number of records {#number-of-records}

By default, Adobe Campaign loads the first 200 records of a list. This means that the display does not necessarily show all the records of the table you are viewing. You can run a count of the number of records in the list and load more records.

In the lower right-hand part of the list screen, a **counter** shows how many records have been loaded and the total number of records in the database (after applying any filters):

![Display total number of records in a list](assets/number-of-records.png)

If a question mark appears instead of the number on the right, such as `240/?`, click the counter to launch the calculation.

To load and display additional records click **[!UICONTROL Continue loading]**. By default, 200 records are loaded. To change the default number of records to load, use the **[!UICONTROL Configure list]** icon in the bottom right-hand corner of the list. In the list configuration window, click **[!UICONTROL Advanced parameters]** (bottom left) and change the number of lines to retrieve.

To load all the records, right-click the list and select **[!UICONTROL Load all]**.

>[!CAUTION]
>
>When a list contains a high volume of records, full loading can take some time.
>

### Add and remove columns {#add-columns}

For each list, the built-in column configuration can be adapted to display more information or hide unused columns.

When data is visible in the detail of a record, right-click the field and select **[!UICONTROL Add in the list]**.

![Add a field in the list](assets/add-in-the-list.png)

The column is added to the right of the existing columns.

![Add a field column](assets/add-a-column.png)

You can also use the list configuration screen to add and remove columns:

1. From a list of records, click **[!UICONTROL Configure list]** icon on the lower right section.
1. Double-click the fields to be added in the **[!UICONTROL Available fields]** list: they are added to the **[!UICONTROL Output columns]** list. 

    ![List configuration screen](assets/list-config-screen.png)


   >[!NOTE]
   >
   >By default, advanced fields are not displayed. To display them, click the **Display advanced fields** icon, on the lower right section of the list of available fields.
   >
   >Fields are identified by specific icons: SQL fields, linked tables, calculated fields, etc. For each field selected, the description is displayed under the list of available fields.
   >

1. Use the up/down arrows to modify the **display order**.

1. Click **[!UICONTROL OK]** to confirm the configuration and display the result.

If you need to remove a column, select it and click the **Trash** icon.

You can use the **[!UICONTROL Distribution of values]** icon to view the repartition of values for the selected field in the current folder.

![](assets/value-distribution.png)


### Create a new column {#create-a-new-column}

You can create new columns to display additional fields in the list. 

To create a column, follow these steps:

1. From a list of records, click **[!UICONTROL Configure list]** icon on the lower right section.
1. Click the **[!UICONTROL Add]** icon to display a new field in the list.
1. Configure the field to add in the column.


### Display data in sub-folders {#display-sub-folders-records}

Lists can display:

* All records contained in the selected folder (default)
* All records contained in the selected folder and its sub-folders

To switch from one display mode to the other, click **[!UICONTROL Display sub-levels]** in the Campaign toolbar.

### Save a list configuration {#saving-a-list-configuration}

The list configurations are defined locally for each user. When the local cache is cleared, local configurations are disabled.

By default, setting parameters apply to all lists with the corresponding folder type. When you modify how the list of recipients is displayed from a folder, this configuration is applied to all the other recipient folders.

You can save more than one configuration to be applied to different folders of the same type. The configuration is saved with the properties of the folder containing the data and can be reapplied.

To save a list configuration so that it can be reused, follow the steps below:

1. From the Explorer, right click the folder containing the displayed data.
1. Select **[!UICONTROL Properties]**.
1. Click **[!UICONTROL Advanced settings]** and then specify a name in the **[!UICONTROL Configuration]** field. 
1. Click **[!UICONTROL OK]** and then click **[!UICONTROL Save]**.

You can then apply this configuration any another folder of the same type. Learn more about folders in [this page](../audiences/folders-and-views.md).

### Export a list {#exporting-a-list}

To export data from a list, you must use an export wizard. To access it, select the elements to be exported from the list, right-click and select **[!UICONTROL Export...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Elements from a list must not be exported using the Copy/Paste function.

### Sort a list {#sorting-a-list}

Lists can contain a large amount of data. You can sort these data or apply simple or advanced filters. Sorting lets you display data in ascending or descending order. Filters let you define and combine criteria to display selected data only.

Click the column header to apply an ascending or descending sort, or to cancel data sorting. Active sort status and sorting order are indicated by a blue arrow before the column label. A red dash before the column label means that the sort is applied to data indexed from the database. This sorting method is used to optimize sort jobs.

You can also configure sorting or combine sort criteria. To do this, follow the steps below:

1. **[!UICONTROL Configure list]** below and to the right of the list. 
1. In the list configuration window, click the **[!UICONTROL Sorting]** tab.
1. Select the fields to sort and the sort direction (ascending or descending).
1. Sort priority is defined by the order of the sort columns. To change the priority, use the appropriate icons to change the order of the columns.

   Sort priority does not affect the display of the columns in the list.

1. Click **[!UICONTROL Ok]** to confirm this configuration and display the result in the list.


## Additional Resources

* **[Start with the Campaign user interface](../start/campaign-ui.md)** - Discover how to access and browse Adobe Campaign interface.
* **[Work with Enumerations](../config/enumerations.md)** - Standardize field values with predefined drop-down lists for faster, more consistent data entry.
