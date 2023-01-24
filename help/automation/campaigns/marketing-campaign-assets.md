---
product: campaign
title: Marketing campaign assets, documents and delivery outlines
description: Learn more about marketing campaign documents and delivery outlines
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
---
# Manage assets and documents {#manage-assets-documents}

You can associate various documents with a campaign: reports, photos, web pages, diagrams, etc. These documents can be in any format.

In a campaign you can also refer to other items, such as promotional coupons, special offers relating to a specific brand or store, etc. When these elements are included in an outline, they can be associated with a direct mail delivery. [Learn more](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>This capability is designed for small assets and documents. 

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Add documents {#add-documents}

Documents can be associated at the campaign level (contextual documents) or the program level (general documents).

For a campaign, the **[!UICONTROL Documents]** tab contains:

* The list of all documents required for the content (template, images, etc.) that can be downloaded locally by Adobe Campaign operators with suitable rights,
* Documents containing information for the router, if any.

The documents are linked to the program or the campaign via the **[!UICONTROL Edit > Documents]** tab. 

![](assets/op_add_document.png)

You can also add a document to a campaign from the dedicated link in the dashboard.

![](assets/add_a_document_in_op.png)

Click the **[!UICONTROL Detail...]** icon to view the content of a file and to add information:

![](assets/add_document_details.png)

In the dashboard, documents associated with the campaign are grouped in the **[!UICONTROL Document(s)]** section, as in the following example:

![](assets/edit_documents.png)

They can also be edited and modified from this view.

## Use delivery outlines {#delivery-outlines}

A delivery outline is structured set of elements (documents, stores, promotional coupons, etc.) created by the company and for a particular campaign. It is used in the context of direct mail deliveries.

These elements are grouped in delivery outlines, and each delivery outline will be associated with a delivery; it will be referenced in the extraction file sent to the **service provider** in order to be attached to the delivery. For example, you can create a delivery outline that refers to a unit and the marketing brochures it uses.

For a campaign, delivery outlines let you structure external elements to be associated with the delivery according to certain criteria: related unit, promotional offer granted, invitation to a local event, etc.

>[!CAUTION]
>
>Delivery outlines are restricted to direct mail campaigns.

### Create a delivery outline {#create-an-outline}

To create a delivery outline, click the **[!UICONTROL Delivery outlines]** sub-tab in the **[!UICONTROL Edit > Documents]** tab of the concerned campaign.

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>If you cannot see this tab, then this capability is not available for this campaign, or the direct mail delivery is not enabled in your instance. Refer to the [campaign template configuration](marketing-campaign-templates.md#campaign-templates) or to your license agreement.

Next, click **[!UICONTROL Add a delivery outline]** and create the hierarchy of outlines for the campaign:

1. Right-click the root of the tree and select **[!UICONTROL New > Delivery outlines]**.
1. Right-click the outline you have just created and select **[!UICONTROL New > Item]** or **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

An outline can contain items, personalization fields, and offers:

* Items can be physical documents, for example, which are referenced and described here and will be attached to the delivery. 
* Personalization fields enable you to create personalization elements related to deliveries rather than recipients. It is thus possible to create values to be used in deliveries for a specific target (welcome offer, a discount, etc.) They are created in Adobe Campaign and imported into the outline via the **[!UICONTROL Import personalization fields...]** link. 

  ![](assets/del-outline-perso-field.png)

  They can also be created directly in the outline by clicking the **[!UICONTROL Add]** icon to the right of the list zone.

  ![](assets/add-del-outline-button.png)


### Select an outline {#select-an-outline}

For each delivery, you can select the outline to associate from the section reserved for the extraction outline, as in the following example:

![](assets/select-delivery-outline.png)

The selected outline is then displayed in the lower section of the window. It can be edited using the icon to the right of the field or altered using the drop-down list:

![](assets/delivery-outline-selected.png)

The **[!UICONTROL Summary]** tab of the delivery also displays this information:

![](assets/delivery-outline-in-dashboard.png)

### Extraction result {#extraction-result}

In the file extracted and sent to the service provider, the name of the outline and, where appropriate, its characteristics (cost, description, etc.) are added to the content according to the information in the export template associated with the service provider.

In the following example, the label, estimated cost, and description of the outline associated with the delivery will be added to the extraction file. 

![](assets/campaign-export-template.png)

The export model must be associated with the service provider selected for the delivery concerned. See [this  section](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures).
