---
title: SMS select the audience
description: Learn how to setup the audience of an SMS delivery
feature: SMS
role: User
level: Beginner, Intermediate
---

# Select the audience of your SMS delivery {#sms-audience}

Before selecting your audience, [learn more about audience here](../../audiences/gs-audiences.md).

In most cases, the main target of a delivery is extracted from Adobe Campaign database (default mode). However, the audience can also be stored in an external file. [Learn more in this section](#external-audience).

## Audience in Adobe Campaign

To select the audience of your delivery, follow the steps below:

1. In the delivery editor, click on **[!UICONTROL To]** link. You will have a **[!UICONTROL Select target]** window opened

1. Because the audience is stored in Adobe Campaign database, in the **[!UICONTROL Main target]** tab, choose **[!UICONTROL Defined in the database]** option.

![](assets/audience_to.png){zoomable="yes"}

1. Select the **[!UICONTROL Target mapping]** in the drop-down list. Adobe Campaign default target mapping is Recipients, based on **[!UICONTROL nms:recipient]** schema.

Other target mappings are available, and some can be related to your specific configuration. For more on target mappings, refer to [Work with target mappings](../../audiences/target-mappings.md).

1. Click the **[!UICONTROL Add]** button to define restriction filters.

You can then select the type of filtering to apply:

![](assets/audience_filters.png){zoomable="yes"}

To use a target type, select it and click **[!UICONTROL Next]** button. 

Here are the target types offered by default:

- **[!UICONTROL Filtering conditions]** : lets you define a query and display the result.
- **[!UICONTROL A list of recipients]** : lets you select a list that you prepared containing your audience
- **[!UICONTROL A recipient]** : lets you select directly a recipient in the table.
- **[!UICONTROL Recipients included in a folder]** : lets you select a folder in the explorer navigation tree
- **[!UICONTROL Recipients of a delivery]** : lets you select the audience of a previous delivery
- **[!UICONTROL Recipients of deliveries belonging to a folder]** : lets you select the audience of all the deliveries in a given folder
- **[!UICONTROL Subscribers of an information service]** : this option lets you select a newsletter to which the recipients must be subscribed to be targeted by the delivery being created.
- **[!UICONTROL User filters]** : lets you use the predefined filters.

The option **[!UICONTROL Exclude recipients from this segment]** lets you target on recipients who do not satisfy the defined target criteria. To use this option, select the appropriate box and then apply targeting, as defined earlier, to exclude the resulting profiles.

1. Enter the name of your audience in the label field, and click on **[!UICONTROL Finish]** button to validate your audience.

![](assets/audience_finish.png){zoomable="yes"}

You can add target population as many as you need in clicking again on **[!UICONTROL Add]** button. You can also delete some of them by clicking on the cross located after their label.

## Audience in an external file {#external-audience}

You can use Adobe Campaign to send a delivery on an audience who is not in its database, but in an external file.

Here are the steps for this : 

1. In the delivery editor, click on **[!UICONTROL To]** link. You will have a **[!UICONTROL Select target]** window opened

1. Choose the **[!UICONTROL Defined in an external file]** option.

![](assets/audience_externalfile.png){zoomable="yes"}

1. By default, recipients are imported in the database. You need to select the **[!UICONTROL Target mapping]** in that case. For more on target mappings, refer to [Work with target mappings](../../audiences/target-mappings.md).

Otherwise, you can also choose **[!UICONTROL Do not import the recipients into the database]**.

1. When importing your file, click the **[!UICONTROL File format definition…]** link to select and configure the external file.

1. Click on **[!UICONTROL Finish]** button to validate your audience.
