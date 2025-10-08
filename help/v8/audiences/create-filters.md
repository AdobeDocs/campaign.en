---
title: Work with filters in Adobe Campaign
description: Learn how to filter your data and save filters in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
version: Campaign v8, Campaign Classic v7
---
# Work with filters{#create-filters}

Data filtering is the process of narrowing down a dataset to only those records that match specific criteria. This subset can then be used for targeted actions (such as updates or audience creation) or for analysis.

When browsing Campaign, data is displayed in lists. You can apply built-in filters to quickly access a defined subset, such as quarantined addresses, untargeted recipients, or records within a specific age range or creation date.

In addition, you can create custom filters, save them for future use, and share them with other Campaign users.

Filters are applied **dynamically**: whenever the data changes, the filtered results are automatically updated.

>[!NOTE]
>
>User interface configuration settings are defined locally at the device level. It may sometimes be necessary to clean up this data, particularly if problems arise when refreshing data. To do this, use **[!UICONTROL File > Clear the local cache]** menu.

The following types of filter are available in Adobe Campaign:

* [Predefined filters](#predefined-filters)
* [Quick filters](#quick-filters)
* [Advanced custom filters](#advanced-filters)

## Predefined filters{#predefined-filters}

### Predefined filters in the dashboards

By default, Adobe Campaign displays all database records that the operator has permission to read. You can filter this data using the options available in the upper section of the browser window.

![](assets/filter_web_zone.png)

There are several ways of filtering the data to be displayed. If necessary, these can be used together. Browse the tabs below to learn more about filtering options.


>[!BEGINTABS]

>[!TAB Filter by folder] 

To filter data based on their folder, click the **[!UICONTROL Folder]** icon and select the folder containing the data to display.

![](assets/filter_web_select_folder.png)

Only the profiles in the folder are displayed:

![](assets/filter_web_folder_display.png)

Use the cross to the right of the folder selection field to return to the default display mode.

>[!TAB Filter by status] 

Depending on the type of information displayed, you can apply a filter by status or by state. 

For example for deliveries, you can choose to display only finished deliveries as shown below:

![](assets/filter_delivery.png)

>[!TAB Order by] 

You can select the sorting order of the data offered on pages via the drop-down list to the right of the 'per folder' filtering field. The content of this field depends on the type of data on the page.

For example, you can sort tasks by priority, creation date, or alphabetical order.

![](assets/order_data_sample.png)

>[!TAB Quick search] 

Use the search field to quickly access the item you are looking for: enter the characters included in the label or internal name of the item you want to display, then confirm to apply an automatic filter to the data on the page.

![](assets/filter_search.png)

To display all items again, click on the cross to delete the content of the search field.

>[!ENDTABS]

### Predefined filters in the Explorer

Predefined filters are available from the **Filters** button above each list.

For example, for the profiles, the following built-in filters are available:
  
![](assets/built-in-filters.png)

You can access the filters details in the **[!UICONTROL Profiles and Targets > Pre-defined filters]** node of the Explorer.

>[!NOTE]
>
>For all other lists of data, predefined filters are stored in the  **[!UICONTROL Administration > Configuration > Predefined filters]** node.

Select a filter to display its definition.

![](assets/predefined-filter-list.png)

Use the last tab to preview the filtered data.

![](assets/built-in-filter-preview.png)


+++  Built-in predefined filters for profiles

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Query</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Opened<br /> </td> 
   <td> Selects recipients who have opened a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Opened but not clicked<br /> </td> 
   <td> Selects recipients who have opened a delivery but have not clicked on a link.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inactive recipients<br /> </td> 
   <td> Selects recipients who have not opened a delivery in X months.<br /> </td> 
  </tr> 
  <tr> 
   <td> Last activity by device type<br /> </td> 
   <td> Selects recipients who have clicked or opened delivery Y using device X in the last Z days.<br /> </td> 
  </tr> 
  <tr> 
   <td> Last activity by device type (Tracking)<br /> </td> 
   <td> Selects recipients who have clicked or opened delivery Y using device X in the last Z days.<br /> </td> 
  </tr> 
  <tr> 
   <td> Untargeted recipients<br /> </td> 
   <td> Selects recipients who have never been targeted via channel Y in X months.<br /> </td> 
  </tr> 
  <tr> 
   <td> Very active recipients<br /> </td> 
   <td> Selects recipients who have clicked in a delivery at least X times in the last Y months.<br /> </td> 
  </tr> 
  <tr> 
 <td> Denylisted email address<br /> </td> 
    <td> Selects recipients whose email address is on the denylist.<br/> </td>
  </tr> 
  <tr> 
   <td> Quarantined email address<br /> </td> 
   <td> Selects recipients whose email address is quarantined.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email addresses duplicated in the folder<br /> </td> 
   <td> Selects recipients whose email address is duplicated in the folder.<br /> </td> 
  </tr> 
  <tr> 
   <td> Neither opened nor clicked<br /> </td> 
   <td> Selects recipients who have not opened a delivery, or clicked in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> New recipients (days)<br /> </td> 
   <td> Selects recipients that were created in the last X days.<br /> </td> 
  </tr> 
  <tr> 
   <td> New recipients (minutes)<br /> </td> 
   <td> Selects recipients that were created in the last X minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> New recipients (months)<br /> </td> 
   <td> Selects recipients that were created in the last X months.<br /> </td> 
  </tr> 
  <tr> 
   <td> By subscription<br /> </td> 
   <td> Selects recipients by subscription.<br /> </td> 
  </tr> 
  <tr> 
   <td> By clicking on a specific link<br /> </td> 
   <td> Selects recipients who clicked on a particular URL in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> By post delivery behavior<br /> </td> 
   <td> Selects recipients according to their behavior after receiving a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> By creation date<br /> </td> 
   <td> Selects recipients by creation date, over a period ranging from X months (current date minus n months) to Y months (current date minus n months).<br /> </td> 
  </tr> 
  <tr> 
   <td> By list<br /> </td> 
   <td> Selects recipients by list.<br /> </td> 
  </tr> 
  <tr> 
   <td> By number of clicks<br /> </td> 
   <td> Selects recipients who clicked in a delivery in the last X months.<br /> </td> 
  </tr> 
  <tr> 
   <td> By number of messages received<br /> </td> 
   <td> Selects recipients according to the number of messages that they received.<br /> </td> 
  </tr> 
  <tr> 
   <td> By number of opens<br /> </td> 
   <td> Selects recipients who opened between X and Y deliveries over Z amount of time.<br /> </td> 
  </tr> 
  <tr> 
   <td> By name or email<br /> </td> 
   <td> Selects recipients according to their name or email.<br /> </td> 
  </tr> 
  <tr> 
   <td> By age range<br /> </td> 
   <td> Selects recipients according to their age.<br /> </td> 
  </tr> 
 </tbody> 
</table>

+++

#### Default filters{#default-filters}

The fields above each list lets you use the **predefined default filter** for this list. For the recipient list, you can filter on the name and email address by default. 

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>The **%** character replaces any character string. For example, enter `%@gmail.com` in the Email field to display all the profiles with a Gmail address. Enter `%@L` in the Last name field to display all the profiles with a L in their last name.

To change the default filter for a recipient list, browse to the **[!UICONTROL Profiles and Targets > Predefined filters]** node.

For all other types of data, configure the default filter via the **[!UICONTROL Administration > Configuration > Predefined filters]** node.

Apply the following steps:

1. Select the filter you want to be used by default.
1. Click the **[!UICONTROL Parameters]** tab and select **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. Uncheck that same option for the current default predefined filter.
1. Click **[!UICONTROL Save]** to apply the filter.
1. Browse to the Recipient folder and click the **[!UICONTROL Remove this filter]** icon on the right of the current filter: the new default filter is available. 
   ![](assets/updated-default-filter.png)


## Quick filters{#quick-filters}

You can set and combine **Quick filters** to build custom filters on specific fields. 

Once added, quick filter fields are displayed above the data list, one after the other. They can be deleted independently of each other.

Quick filters are specific to each operator and are re-initialized each time the operator clears the cache of their Client Console.

If you need to reuse a filter, create an **advanced filter** and save it. [Learn more](#advanced-filters).

To create a **quick filter**, follow these steps:

1. Right-click the field you want to filter and select **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   The default filter fields are displayed above the list.

   ![](assets/quick-filter-above-list.png)

1. Select the filter options.
1. If needed, use the grey icon on the right side of a filter to remove it.
1. You can combine filters to refine your filter.

   ![](assets/add-filter-above-the-list.png)


If you need to filter on a field which is not available in the form, but in the columns, and filter on that column. To do this,

1. Click the **[!UICONTROL Configure list]** icon.

   ![](assets/configure-list.png)

1. Select the column to display, for example the age of the recipients, and click **Ok**.

   ![](assets/add-age-column.png)

1. Right-click the **Age** column in the recipient list, and select **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   You can then select the age filtering options. Add another filter on the age to define a range.

   ![](assets/filter-on-age.png)

## Advanced filters{#advanced-filters}

Combine complex criteria in custom **Advanced filters**. Use these filters to create a complex query or a combination of queries on your data. These filters can be saved and shared with other Campaign users.

### Create an advanced filter{#create-adv-filters}

To create an **advanced filter**, click the **[!UICONTROL Filters]** button and select **[!UICONTROL Advanced filter...]**. 

![](assets/adv-filter.png)

You can also right-click the list of data and select **[!UICONTROL Advanced filter...]**.

Define the filtering conditions. In the example below, you will filter on recipients whose Account number does not start with NL, and who live in Paris or Los Angeles.

1. Click the **[!UICONTROL Edit expression]** icon of the **[!UICONTROL Expression]** column.

   ![](assets/edit-exp.png)

1. Select the field to filter on.
1. Select the operator to be applied from the drop-down list.

   ![](assets/select-operator.png)

1. Select an expected value from the **[!UICONTROL Value]** column. You can combine several filters to refine your query. To add a filter condition, click **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

    >[!NOTE]
    >
    >You can assign a hierarchy to the expressions or change the order of the query expressions using the toolbar arrows.

1. Three operators are available to combine expressions:  **And**, **Or**, **Except**. Click the arrow to switch to **Or**.

   ![](assets/select-or-operator.png)

1. Click **[!UICONTROL Ok]** to create the filter and apply it to the current list.

The filter applied is displayed above the list.

![](assets/adv-filter-link.png)

To edit or modify this filter, click its description link in blue, above the list.


### Save an advanced filter{#save-adv-filters}

You can save an advanced filter as a  [predefined filter](#predefined-filters), so that you can reuse it and share it with the other Campaign users.

To save an advanced filter, follow the steps below:

1. Click the description of the filter to edit it.
1. Click the **[!UICONTROL Save as filter]** icon on the upper right section of the window.

   ![](assets/save-as-filter.png)

1. Enter a name for this filter and save it.

   ![](assets/application-filter-save.png)

The filter is added to the [predefined filters](#predefined-filters). It can be updated from this node.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>You can add a shortcut for your filter to activate it from your keyboard. 



This filter is also available from the predefined filters of the recipient list.

![](assets/access-to-new-predefined-filter.png)



### Use a filter to define a segment {#filter-as-segment}

You can use and combine filters to create a target population segment.

Once saved, advanced filters are available when selecting the target population of a message, in the **[!UICONTROL User filters]** section.

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Use the **[!UICONTROL Exclude recipients from this segment]** to target only contacts who do not match the filter criteria.


### Use functions to build advanced filters{#use-functions-adv-filters}

To perform advanced filtering capabilities, use functions to define the content of the filter. The Advanced filter editor leverages all capabilities of Campaign query editor.  

Learn how to build advanced queries in these end-to-end samples:

* Learn how to target on simple recipient attributes in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.
* Learn how to filter on recipients not contacted during the last 7 days in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html){target="_blank"}.
* Learn how to recover the list of operators can be filtered by Active accounts in [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html){target="_blank"}.
* Learn how to build a birthday email audience in  [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html){target="_blank"}.


### Advanced parameters for predefined filters {#param-for-data-filters}

Advanced parameters are available for predefined filters. To access them, browse to the **[!UICONTROL Parameters]** tab of the filter.

* To display the filter by default for all the lists based on this Document type, select the **[!UICONTROL Default filter for the associated document type]** option.

  For example, the **[!UICONTROL By name or login]** filter is applied to operators This option is selected, so the filter is always displayed on all operator lists.

* To make a filter available to all Campaign operators, select the  **[!UICONTROL Filter shared with other operators]** option.

* To define a form to select the filtering criteria, select the  **[!UICONTROL Use parameter entry form]** option. This form must be entered in XML format in the **[!UICONTROL Form]** tab. For example, the built-in predefined filter **[!UICONTROL Recipients who have opened]**, available from the recipients list, displays a filter field that lets you select the delivery to which the filter applies to.

![](assets/predefined-filters-parameters.png)


* The **[!UICONTROL Advanced parameters]** link lets you define additional settings. 
    
    * You can associate a SQL table with the filter to make it common to all editors that share the table.
    * To prevent any user from overriding the filter, select the **[!UICONTROL Do not restrict the filter]** option. For example, this option is active for "Recipients of a delivery" and "Recipients of deliveries belonging to a folder" filters which are available in the delivery wizard. These filters cannot be overloaded.

