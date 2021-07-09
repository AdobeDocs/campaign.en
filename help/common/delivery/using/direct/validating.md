---
product: campaign
title: Direct mail data extraction
description: Direct mail data extraction
audience: delivery
content-type: reference
topic-tags: sending-direct-mail
exl-id: 42bb395b-b3fe-4d48-8720-5a4cae191984
---
# Validate the extraction{#validating}

Global concepts when validating a delivery are presented in [this section](../steps-validating-the-delivery.md).

The output file of a direct mail delivery is generated during the [delivery analysis](../steps-validating-the-delivery.md#analyzing-the-delivery). The file content depends on the selected output columns. [Learn more](defining-the-direct-mail-content.md#extraction-file)).

During the analysis phase, the file is generated but recipients delivery logs are not updated.

Check the result of the analysis and the content of the output file before clicking **[!UICONTROL Confirm delivery]**. A confirmation message lets you launch the delivery.

When you confirm sending, the data extraction in the specified file starts.

![](../assets/s_ncs_user_postal_del_send_confirm_postal.png)

You can then close the wizard and look at the delivery logs via the **[!UICONTROL Delivery]** tab, accessible via the delivery details.

You can configure the delivery logs retrieval mode from the **[!UICONTROL Analysis]** tab of the delivery properties.

There are two modes:

* **[!UICONTROL Messages are considered sent after validation]** (default mode) - in this mode, all broadlogs are updated when the operator confirms the send (their status passes from 'Pending delivery' to 'Sent') and the delivery is automatically set to **[!UICONTROL Finished]**.
* **[!UICONTROL A file of results determines the messages that are sent and those that have failed]** - this mode allows you to update the broadlogs via an external file sent by the service provider. In this case, a workflow to process this information needs to be used in order to update the broadlog status.

>[!NOTE]
>
>In this case, the delivery's status also needs to be changed to **[!UICONTROL Finished]** by the user as soon as the broadlogs are updated.
