---
title: Campaign interface settings
description: Learn how to customize Campaign interface settings
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
exl-id: fefb6d80-c3d1-448b-82ab-648da58a0ba4
---
# Campaign user interface settings {#ui-settings}

## Enumerations {#enumerations}

An enumeration (also known as 'itemized list') is a list of values suggested by the system to populate fields. Use enumerations to standardize the values of these fields, help with data input or use within queries.

The list of values appears as a drop-down list from which you can select the value to be entered in the field. The drop-down list also enables predictive input: enter the first letters, and the application fills in the rest.

The values for this type of field are defined and overall administration of these fields (adding/deleting a value) is performed via the **[!UICONTROL Administration > Platform > Enumerations]** node of the tree.

![Access enumerations](assets/enumerations-menu.png)

### Types of enumerations {#types-of-enum}

Enumerations are stored in the **[!UICONTROL Administration > Platform > Enumerations]** folder of the explorer. 

They can be: Open, System, Emoticon or Closed.

* An **Open** enumeration allows users to add new values directly in the fields based on this enumeration.
* A **Closed** enumeration has a fixed list of values which can only be modified from the **[!UICONTROL Administration > Platform > Enumerations]** folder of the explorer. 
* An **Emoticon** enumeration is used to update the emoticon list. Learn more
* A **System** enumeration is associated to system fields and is coming with an Internal name.

For **Open** and **Closed** enumerations, specific options are available:

* **Simple enumeration** is the default standard type.
* **Alias cleansing** enumeration is used to harmonize the enumeration values stored in the database. [Learn more](#alias-cleansing)
* **Reserved for binning** is an option which allows you to link cube values to this enumeration. [Learn more](../reporting/gs-cubes.md)


### Alias cleansing {#alias-cleansing}

In the enumeration fields, you can select a value, or enter a custom value which is not available in the drop-down list. Custom values can be added to the existing enumerations values, as a new one - in this case, the **[!UICONTROL Open]** option must be selected. These custom values can be cleaned using alias cleansing capabilities. For example if a user enters `Adob` instead of `Adobe`, alias cleansing process can automatically replace it by the correct term.

>[!CAUTION]
>
>Data cleansing is a critical process that impacts the data in the database. Adobe Campaign carries out mass data updates, which may lead to some values being deleted. This operation is therefore reserved for expert users.

Enable the **[!UICONTROL Alias cleansing]** option to use data cleansing capabilities for an enumeration. When this option is selected, the **[!UICONTROL Alias]** tab is displayed at the bottom of the window. 

When a user enters a value which does not exist in an Alias cleansing enumeration, it is added to the **Values** list. You can [create aliases from these values](#convert-to-alias), or [create new aliases from scratch](#create-alias).

#### Create an alias{#create-alias}

To create an alias, follow these steps:

1. Click **[!UICONTROL Add]** button of the **[!UICONTROL Alias]** tab.
1. Enter the alias you want to convert and select the value to be applied in the drop-down list. 

    ![Create a new alias](assets/new-alias.png)

1. Click **[!UICONTROL Ok]** and confirm.
    
1. Save your changes. The replacement of values is performed by the **Alias cleansing** workflow which is executed every night. Refer to [Run data cleansing](#running-data-cleansing).

For all fields based on this enumeration, when a user enters the value **Adob** in a "company" field (in the Adobe Campaign console, in a web form), it will automatically be replaced by the value **Adobe**.

#### Convert a wrong value to an alias{#convert-to-alias}

You can also convert an existing enumeration value into an alias. To perform this:

1. In the list of values of an enumeration, right-click and browse to **[!UICONTROL Actions... > Convert values into aliases...]**. 

    ![Convert a value to an alias](assets/convert-into-aliases.png)

1. Select the values to be converted in aliases and click **[!UICONTROL Next]**.
1. Click **[!UICONTROL Start]** to run the conversion.

    Once execution is complete, aliases are added to the list, in the **Alias** tab. You can associate a correct value to replace wrong entries. To perform this: 

1. Select a value to clean.
1. Click the **Detail...** button.
1. Select the new value in the drop-down list.

    ![Create a new alias](assets/define-new-alias.png)


>[!NOTE]
>
>You can track the occurrences of an alias in the **[!UICONTROL Hits]** column in the **[!UICONTROL Alias]** sub-tab. It can display the number of times this value was entered.  [Learn more](#calculate-entry-occurrences).

#### Run data cleansing {#running-data-cleansing}

Data cleansing is performed by the **[!UICONTROL Alias cleansing]** technical workflow. By default, it is executed on a daily basis.

Cleansing can also be triggered via the **[!UICONTROL Cleanse values...]** link.

The **[!UICONTROL Advanced parameters...]** link lets you set the date starting from which collected values are taken into account.

Click the **[!UICONTROL Start]** button to run data cleansing.

##### Monitor occurrences {#calculate-entry-occurrences}

The **[!UICONTROL Alias]** sub-tab of an enumeration can display the number of occurrences of an alias among all the values entered. This information is an estimate and will be displayed in the **[!UICONTROL Hits]** column.

>[!CAUTION]
>
>Calculating alias entry occurrences can take a long time.
>

You can run hit calculation manually via the **[!UICONTROL Cleanse values...]** link. To do this, click the **[!UICONTROL Advanced parameters...]** link and select option(s).

* **[!UICONTROL Update the number of alias hits]**: this lets you update hits which have already been calculated, based on the entered date.
* **[!UICONTROL Recalculate the number of alias hits from the start]**: lets you run calculation on the entire Adobe Campaign platform.

You can also create a dedicated workflow in order for the calculation to run automatically for a given period, once a week for example.

To do this, create a copy of the **[!UICONTROL Alias cleansing]** workflow, change the scheduler and use the following settings in the **[!UICONTROL Enumeration value cleansing]** activity:

* **-updateHits** to update the number of alias hits,
* **-updateHits:full** to recalculate all alias hits.
