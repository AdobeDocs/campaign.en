---
product: campaign
title: Cells
description: Cells
feature: Workflows, Targeting Activity
role: User
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
---
# Cells{#cells}

The **[!UICONTROL Cells]** activity provides a view of the various subsets as data columns. It facilitates subset manipulation and is also designed to leverage personalization capabilities.

![](assets/wf_split_cells.png)

This activity can be configured to enter specific parameters based on user needs. By default, the detail of each subset is detailed in a dedicated window via the **[!UICONTROL Cells]** and **[!UICONTROL Advanced]** tabs. 

![](assets/wf_split_cells_with_customization.png)

In the example below, the input form has been modified: a **[!UICONTROL Data]** tab has been added to enable the association of an offer and a priority level for each subset.

![](assets/cells-activity-sample.png)

For this configuration, the following information was added to the workflow form, in the **[!UICONTROL Administration > Configurations > Input forms]** node of Adobe Campaign explorer:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

Input form personalization in Adobe Campaign is reserved for expert users. 