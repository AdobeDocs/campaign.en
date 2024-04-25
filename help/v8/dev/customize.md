---
title: Customize your instance
description: Learn how to customize your instance
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
---
# Customize your instance {#gs-ac-custom}

Learn how to **Customize your Campaign instance**.

>[!CAUTION]
>
>Adobe Campaign customization is reserved to expert users only. 

## Create new data fields and schemas

Adobe Campaign makes use of Data Schemas to:

* Define how data objects within the application are tied to underlying database tables
* Define links between the different data objects within the Campaign application
* Define and describe the individual fields included in each object

For example, to add a field to an existing table, such as the recipient table (nms:recipient), you have to extend that schema. 

Two table extension modes are available:

* Through the interface, by using the **New field** assistant

    Learn how to quickly add a new field in Campaign in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html#configuring-campaign-classic){target="_blank"}

* Programmatically, by extending the schema. Learn how to extend an existing schema in [this section](../dev/extend-schema.md).

You can also create new tables in the Campaign database and extend the built-in datamodel.

To add an entirely new type of data that does not exist out-of-the-box in Adobe Campaign (a table of contracts for example) you can create a custom schema directly. For more on this, refer to [this example](../dev/create-schema.md#example--creating-a-contract-table).

**Related topics**

Example of schema edition in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#configuring-campaign-classic){target="_blank"}

Use Case: link a field to an existing reference table in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#uc-link){target="_blank"}


## Modify the input forms

Campaign input forms can be adapted to adapt to your implementation. You can add or remove form fields by modifying the XML content.

Learn how to modify an existing input form or create a new form in [this section](../dev/forms.md).

## Customize dashboards{#gs-custom-dashboards}

The Adobe Campaign interface uses many Web applications to access, manage, and interact with recipients, deliveries, campaigns, stocks, etc. They are seen in the interface in the form of dashboards with only one page.

The built-in Web applications are stored in the **Administration > Configuration > Web applications** folder of the Explorer.

Learn how to create an overview page in Campaign in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html#creating-a-single-page-web-application){target="_blank"}


## Customize lists and create filters {#gs-lists-and-filters}

Campaign lists come with pre-defined filters to facilitate navigation and data vizualisation. 

When you navigate in the Adobe Campaign Explorer tree, the data contained in the database is displayed in lists. You can filter these lists, run searches, add information, filter and sort data.

Learn how to configure lists and save a list configuration in [this page](../start/campaign-ui.md).

You can apply filter on these lists to display only the data needed by the operator. Then actions can then be executed on the filtered data. Filter configuration lets you select data from a list dynamically. If the data is modified, the filtered data is updated.

Learn more about filtering options in [this page](../audiences/create-filters.md).
