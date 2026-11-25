---
product: campaign
title: Use cubes to create reports on data
description: Learn how to use cubes to create reports
feature: Reporting
role: User, Developer
level: Beginner
exl-id: 7dbc66ab-a468-40ff-9db2-b33e4fd27754
TQID: 'https://experienceleague.adobe.com/fVo8tGw-kPgGgB7djOQr8tv5MoRvrPr-MF2bzYYKDgI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Use cubes to explore data{#use-cubes-to-create-reports}

Use cubes to create reports, and to identify and select data from the database. You can:

* Create reports based on cubes. [Learn more](#explore-the-data-in-a-report).
* Collect the data in the database and group it into lists, for instance to identify and build targets and deliveries. [Learn more](#build-a-target-population).
* Insert a pivot table into a report, reference an existing cube in it. [Learn more](#insert-a-pivot-table-into-a-report).

## Explore the data in a report {#explore-the-data-in-a-report}

### Step 1 - Create a report based on a cube {#step-1---create-a-report-based-on-a-cube}

Once the [cube is configured](cube-indicators.md), it can be used as a template for creating a new report.

To create a report based on an existing cube, follow the steps below:

1. Click the **[!UICONTROL Create]** button of the **[!UICONTROL Reports]** tab and select the cube you have just created.

   ![Creating a new report page with the New Client Profile cube template selected and the Create button](assets/new-report-based-on-cube.png)

1. Click the **[!UICONTROL Create]** button to confirm: this will take you to the report configuration and viewing page.

   By default, the first two available dimensions are offered in lines and columns but no value is displayed in the table. To generate the table, click the main icon:

   ![New Client Profile report with Age and Creation date axes and the icon to display the pivot table](assets/cube-report-config.png)

1. You can switch the axes of the dimension, delete them, add new measures, etc. To do this, use the appropriate icons.

   ![Creation date dimension dragged from the left axis to the top axis next to Age in the New Client Profile report](assets/cube-switch-axis.png)

   These operations are detailed below.

### Step 2 - Select lines and columns {#step-2---select-lines-and-columns}

The default display shows the first two dimensions of the cube (age and city, in this case).

The **[!UICONTROL Add]** buttons on each axis enable you to add dimensions. 

![Add button on the lines axis of the New Client Profile report for adding a dimension](assets/cube-switch.png)

1. Select the dimensions to display in the lines and columns of the table. To do this, drag and drop the available dimensions.
1. Select the dimensions that you want to add to the table from the list:
   ![Add a dimension to the column dialog listing City, Country, Last Purchase Date and Purchases Amount](assets/cube-select-dimension.png)

1. Then select the parameters of this dimension. 

   ![Dimension settings for City: Label, Expand during loading, Sort data, order and Number of lines shown](assets/cube-dimension-param.png)

   These parameters depend on the data type of the selected dimension.

   For instance, for dates, several levels can be available. For more on this, refer to [Display measures](customize-cubes.md#display-measures).

   In that case, the following options are available:

   ![Date dimension settings per level, Year and Month, including Format Long or Short](assets/cube-config.png)

   You can either:

    * Expand data during loading: the values will be displayed by default each time the report is updated (default value: no).
    * Display the total at the end of the line: when the data is displayed in columns, an additional option lets you display the total at the end of the line: a column is added to the table (default value: yes).
    * Apply a sort: the values of the column can be sorted according to value, label, or based on a measure (default value: by value).
    * Display the values in ascending (a-z, 0-9) or descending (z-a, 9-0) order.
    * Change the number of columns to be displayed upon loading (by default: 200).

1. Click **[!UICONTROL Ok]** to confirm: the dimension is added to the existing dimensions.

   The yellow banner above the table shows that you have made changes: click the **[!UICONTROL Save]** button to save them.

   ![City added to the lines axis, with the yellow banner prompting you to Save the report changes](assets/cube-in-report.png)

### Step 3 - Configure the measures to display {#step-3---configure-the-measures-to-display}

Once the lines and columns are defined, select which measures you want to display. By default, only one measure is displayed. 

To add and configure measures, follow the steps below:

1. Click the **[!UICONTROL Measures]** button. 

   ![Measures button opening the Configure measures dialog with Label, Formatting and Unit options](assets/cube-measure-button.png)

1. With the **[!UICONTROL Use a measure]** button, select one of the existing measures.

   ![Add an existing measure to the pivot table dialog listing French, German, Men and Women](assets/cube-add-measure.png)

   Choose the information to display and the formatting options. The list of options depends on the type of measure.

   ![Configure measures dialog with Formatting options Number and Percentage and Edit the dynamic measure button](assets/cube-measure-options.png)

   Overall measure configuration is also available via the **[!UICONTROL Edit the configuration of the pivot table]** icon in the header.

   ![Edit the pivot table configuration icon in the report toolbar](assets/cube-pivot-table-config.png)

   You can then choose whether or not to display measure labels. [Learn more](customize-cubes.md#configuring-the-display).

1. You can build new measures based on existing ones. To do this, click **[!UICONTROL Create a measure]** and configure it.

   ![Creating a dynamic measure dialog with the Combination of measures type, operator and two measures](assets/cube-create-new-measure.png)

   The following types of measures are available:

    * Combination of measures: this type of measure enables you to build the new measure using existing ones:

      The available operators are: sum, difference, multiplication and rate.
    
    * Proportion: this type of measure enables you to calculate the number of records measured for a given dimension. You can calculate the proportionality based on a dimension or sub-dimension.
    * Variation: this measure lets you calculate the variation in values of a level.
    * Standard deviation: this type of measure lets you calculate deviations within each group of cells compared to the average of the values. For instance, you could compare the purchase volume for all existing segments.

   Once created, the measure is added to the report.

   ![Pivot table showing the new German & English measure next to Men and Women, by Company](assets/cube-display-new-measure.png)

   Once you have created a measure, you can edit it and change its configuration. To do this, click the **[!UICONTROL Measures]** button, then browse to the tab of the measure to edit.

   Then click **[!UICONTROL Edit the dynamic measure]** to access the settings menu.

## Build a target population {#build-a-target-population}

Reports built using cubes enable you to collect data from the table and save it in a list.

To group a population into a list, follow the steps below:

1. Click the cells that contain the population to be collected to select them, then click the **[!UICONTROL Add to cart]** icon.

   ![Add to cart icon in the toolbar of the CLIENTS pivot table with selected cells](assets/cube-add-to-cart.png)

   Do this as many times as necessary to collect various profiles.

1. Click the **[!UICONTROL Show cart]** button to view its content before running the export.

   ![Show cart button opening the Cart details dialog with cart items and the Export button](assets/cube-show-cart.png)

1. Use the **[!UICONTROL Export]** button to group the items in the cart into a list.

   Enter the name of the list and select the type of export to carry out.

   ![Export cart 1/2 dialog with export into a new list, Label, Folder and Export type, and Start button](assets/cube-export-report.png)

   Click **[!UICONTROL Start]** to run the export.

1. Once the export is complete, a message confirms its execution and the number of records that have been processed.

   ![Export cart 2/2 dialog confirming Export finished with the number of records, and Close buttons](assets/cube-export-confirm.png)

   You can either save the content of the cart or empty it.

   The new list is available via the **[!UICONTROL Profiles and targets]** tab.

   ![Lists page under Profiles and targets showing the new GOLD recipients list](assets/cube-list-available.png)

## Insert a pivot table into a report {#insert-a-pivot-table-into-a-report}

To create a table and explore the data in a cube, follow the steps below:

1. Create a new report with a single page and insert a pivot table into it. 

   ![Report editor with a Page activity and the Pivot table option in the toolbar menu](assets/cube-insert-in-report.png)

1. In the **[!UICONTROL Data]** tab of the page, select a cube to process the dimensions it contains and display calculated measures.

   ![Data tab of the pivot table with the New Client Profile cube selected in the Cube field](assets/cube-selected-in-report.png)

   This lets you build the report to be displayed. For more on this, refer to [Step 2 - Select lines and columns](#step-2---select-lines-and-columns).
