---
product: campaign
title: Inbound SMS
description: Learn more about the Inbound SMS workflow activity
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2c12c45b-4429-4e60-bc96-ff70a95d4c9e
TQID: https://experienceleague.adobe.com/ZZcWkqyokq5qWLAHGLW7TNJimNc5a9MUEQkSr0fgKgc
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
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Inbound SMS{#inbound-sms}



The **Inbound SMS** activity lets you download and process text messages from an external account.

## Properties {#properties}

![](assets/sms_rec_edit.png)

The first tab of the **Inbound SMS** activity lets you enter the routing parameters for SMS messages and enter the script to be executed on receiving each message. The second tab lets you assign a schedule to the activity, and the third tab defines the expiration conditions of the activity.

1. **[!UICONTROL SMS routing]**: Select the external account to be used for SMS recovery. External accounts are configured via the **[!UICONTROL Administration > Platform > External accounts]** node of the tree. [Learn more](../../v8/config/external-accounts.md)
1. **[!UICONTROL Script]** 
1. **[!UICONTROL Schedule]** 

   ![](assets/sms_rec_edit_2.png)

1. **[!UICONTROL Expiration]**

The **[!UICONTROL Script]**, **[!UICONTROL Schedule]** and **[!UICONTROL Expiry]** tabs are detailed in [Inbound Emails](inbound-emails.md).
