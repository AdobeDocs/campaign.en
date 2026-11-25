---
product: campaign
title: Get started with web forms
description: Get started with web forms in Campaign
feature: Landing Pages, Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 63602bed-ace6-4632-a735-5d268a7d72d0
TQID: 'https://experienceleague.adobe.com/0pFZXTesqvdOPLrqbW4dRx2O0WR0RaoBnwVyQl9FZDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Get started with web forms{#about-web-forms}

 

Adobe Campaign integrates a graphical module for defining and publishing Web forms to create pages containing input and selection fields, and which may include data in the database. This lets you design and post Web pages which users can access to view or enter information.

This chapter details the creation and management of Web forms, how to manage fields and pages, as well as storage and saving modes.

>[!CAUTION]
>
>For privacy reasons, we recommend to use HTTPS for all external resources.

## Steps for creating a web form {#steps-for-creating-a-web-form}

This chapter details the steps required for designing a **webForm** type form in Adobe Campaign, as well as the available options and configurations. Adobe Campaign lets you make this Web form available to users as well as collect and archive answers in the database.

>[!CAUTION]
>
>When configuring web applications and webforms, you need a 900 pixel vertical resolution minimum (ex: 1600x900).

Web forms are accessed via the Web Applications menu of the **Campaigns** tab. In the Adobe Campaign tree, they are grouped under the **[!UICONTROL Resources > Online > Web Applications]** node.

To create a Web form, click the **[!UICONTROL Create]** button above the list of Web applications.

![Web applications list under Campaigns with the Create button highlighted for starting a new web form.](assets/webapp_create_new.png)

Select the Web form template ( **[!UICONTROL newWebForm]** by default).

![New Web application dialog with the New Web form (newWebForm) template selected in the Template list.](assets/s_ncs_admin_survey_select_template.png)

This will take you to the dashboard of the form. 

![Dashboard tab of a new web form showing its status, schema, folder, public URL and the Publish button.](assets/webapp_empty_dashboard.png)

The **[!UICONTROL Edit]** tab lets you create your content.

![Edit tab of a web form showing the diagram of activities (Start, Page, Test, Storage, End) and the activity palette.](assets/webapp_edit_tab.png)

To define the configuration and content of the Web form, apply the following steps:

* Start by creating the required pages and controls: input fields, drop-down lists, HTML content, etc.

  This step is detailed below.

* Define page sequencing and condition the display.

  This step is detailed in [Defining web forms page sequencing](defining-web-forms-page-sequencing.md).

* Translate the content if necessary.

  This step is detailed in [Translating a web form](translating-a-web-form.md).

## About web forms designing {#about-web-forms-designing}

The pages of the form are created via a specific editor which lets you define and configure input zones (text), selection fields (lists, checkboxes, etc.) and static elements (images, HTML contents, etc.). They can be grouped into containers and their layout altered to suit your needs (for more on this, refer to [Creating containers](defining-web-forms-layout.md#creating-containers)).

The following sections detail how to define content and layout for form screens:

* [Adding fields to a web form](adding-fields-to-a-web-form.md),
* [Inserting HTML content](static-elements-in-a-web-form.md#inserting-html-content),
* [Static elements in a web form](static-elements-in-a-web-form.md),
* [Defining web forms layout](defining-web-forms-layout.md).

>[!NOTE]
>
>* During page design, you can view the final rendering in the **[!UICONTROL Preview]** tab. To view changes, save the form first. Any errors are displayed in the **[!UICONTROL Log]** tab.
>* To make sure page display and information storage occur in the appropriate sequence, enable debug mode in the Web form. To do this, go to the **[!UICONTROL Preview]** sub-tab and check the **[!UICONTROL Enable debug mode]** box: all collected information and possible execution errors will be displayed at the bottom of each page.
>

### Using the icons in the toolbar {#using-the-icons-in-the-toolbar}

You can also use the icons in the toolbar or a right-click to insert an input zone. 

![Page editor toolbar menu for adding an input field: Combo box, Checkbox, Radio button, Multiple choice, Date, Grid.](assets/s_ncs_admin_webform_add_selection.png)

In this case, start by selecting the type of field to add and the answer storage mode.

![Storage dialog: choose Edit a recipient or Variable, then pick the Database field with Edit expression.](assets/s_ncs_admin_webform_select_storage.png)

Click **[!UICONTROL Ok]** to approve the selection. 

![Selecting the Salutation field in Select an expression fills the Database field in the Storage dialog; click Ok.](assets/s_ncs_admin_webform_confirm_storage.png)
