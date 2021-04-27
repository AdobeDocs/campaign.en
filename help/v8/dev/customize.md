---
solution: Campaign Classic
product: campaign
title: Customize your instance
description: Learn how to customize your instance
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
---
# Customize your instance{#gs-ac-custom}

Learn how to **Customize your Campaign instance**

>[!CAUTION]
>
>Adobe Campaign customization is reserved to expert users only. 


## Create new data fields and schemas

Adobe Campaign employs Data Schemas to:

* Define how data objects within the application are tied to underlying database tables
* Define links between the different data objects within the Campaign application
* Define and describe the individual fields included in each object

You can add a field to an existing table, such as the recipient table (nms:recipient), you have to extend that schema. 

Two table extension modes are available:

* Through the interface, by using the New field assistant

    :arrow_upper_right: Learn how to quickly add a new field in Campaign in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programmatically, by extending the schema

    :arrow_upper_right: Learn how to extend an existing schema in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/extending-a-schema.html?lang=en#configuring-campaign-classic)


You can create new tables in Campaign database and extend built-in datamodel.

To add an entirely new type of data that does not exist out-of-the-box in Adobe Campaign (a table of contracts for example) you can create a custom schema directly. For more on this, refer to [this example](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/data-schemas.html?lang=en#example--creating-a-contract-table).

**See also**

:arrow_upper_right: [Example of schema edition](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

:arrow_upper_right: [Use Case: link a field to an existing reference table](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modify the input forms

Campaign input forms can be adapted to fit with your implementation. You can add or remove fields by modifying the XML content.

:arrow_upper_right: Learn how to modify an existing input form in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/input-forms/editing-forms.html?lang=en#configuring-campaign-classic)

:arrow_upper_right: Discover input form customization options in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/input-forms/form-structure.html?lang=en#formatting)


## Customize dashboards{#gs-custom-dashboards}

The Adobe Campaign interface uses many Web applications to access, manage, and interact with recipients, deliveries, campaigns, stocks, etc. They are seen in the interface in the form of dashboards with only one page.

The out-of-the-box Web applications are stored in the Administration > Configuration > Web applications node.

:arrow_upper_right: Learn how to create an overview page in Campaign in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Customize lists and create filters {#gs-lists-and-filters}

### Access data from dashboards

Campaign lists come with predefined filters to facilitate navigation and data vizualisation. 

:arrow_upper_right: Learn more about filtering options in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Access data from the Explorer

When you navigate in the Adobe Campaign Explorer tree, the data contained in the database is displayed in lists. You can filter these lists, run searches, add information, filter and sort data.

:arrow_upper_right: Learn how to configure lists and save a list configuration in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


You can apply filter on these lists to display only the data needed by the operator. Then actions can then be executed on the filtered data. Filter configuration lets you select data from a list dynamically. If the data is modified, the filtered data is updated.

:arrow_upper_right: Learn how to filter data in [this page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
