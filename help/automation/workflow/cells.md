---
product: campaign
title: Cells
description: Cells
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
TQID: https://experienceleague.adobe.com/io5sW8Sd5PlrMn4F6i-wdM05BeZiQ5FX6KPl2ncymQU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
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