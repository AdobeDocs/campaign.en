---
title: SMS in a mid-sourcing infrastructure
description: Learn how to configure a SMS delivery in a mid-sourcing infrastructure
feature: SMS
role: User
level: Beginner, Intermediate
---

# SMS in a mid-sourcing infrastructure {#sms-mid}

Sending SMS deliveries with a mid-sourcing infrastructure requires : 

1. An SMS Operator used for the SMS external account created on the Marketing server. [Learn how to create it here](#sms-operator-mid)
1. An SMS external account on the Marketing server, specifying the Channel and Mid-sourcing Delivery mode.[Learn how to create it here](#sms-operator-mid)
On the **Marketing server** : 
* An external account specifying the channel and the delivery mode
* A delivery template that references the external account to streamline the sending process.

On the **Mid-server** :

* An external account detailing the connector and message type.

To send to a mobile phone with mid-servers, you need:





An external account on the Mid-server, detailing the connector and message type.

A delivery template that references the external account to streamline the sending process.

## Create the SMS operator on the Mid-server {#sms-operator-mid}

First, you need to create an SMS operator on the Mid-server, that will be used by the SMS external account on the Marketing server.

>[!IMPORTANT]
>
>Each SMS connector requires a unique SMS operator

To create you SMS operator, follow the steps below : 

1. In **[!UICONTROL Administration]** > **[!UICONTROL Access management]** > **[!UICONTROL Operators]**, click on the **[!UICONTROL New]** and fill in the form in the new window opened. 

**[!UICONTROL Name (login)]** and **[!UICONTROL Label]** are mandatory.
Password is not mandatory but highly recommended for the security.

Note that the Name (login) is to be later used to name your SMPP external account in the Mid-server.

![](assets/smsoperator_mid.png){zoomable="yes"}

2. In **[!UICONTROL Groups and named rights]** part, click on **[!UICONTROL Add]** button.
On the new window opened, choose **[!UICONTROL Named rights]** in the **[!UICONTROL Folder]** list, and select **[!UICONTROL ADMINISTRATION]** in the right list.
Click on **[!UICONTROL Ok]** button.

![](assets/smsoperator_rights.png){zoomable="yes"}

3. Click on **[!UICONTROL Save]** button to finalize the creation of your SMS operator. 

![](assets/smsoperator_save.png){zoomable="yes"}

You can see it in the operators list now.

![](assets/smsoperator_list.png){zoomable="yes"}

## Create an SMS external account on the Marketing server {#sms-external-account}

In a mid infrastructure, you need to create a SMS external account on the Marketing serve as below

>[!IMPORTANT]
>
>Using the same account and password for multiple external SMS accounts can result in conflicts and overlap between the accounts. Learn more on [SMS troubleshooting page](smpp-connection.md#sms-troubleshooting). 

1. In **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**, click the **[!UICONTROL New]** icon

![](assets/sms_extaccount.png){zoomable="yes"}

1. Set up the **[!UICONTROL Label]** and the **[!UICONTROL Internal name]** of your external account. Define the account type as **[!UICONTROL Routing]**, check the **[!UICONTROL Enabled]** box, select **[!UICONTROL Mobile (SMS)]** for the channel, and **[!UICONTROL Mid-sourcing]** for the delivery mode.

![](assets/mid_smsextaccount.png){zoomable="yes"}

1. In the **[!UICONTROL Mid-sourcing]** tab, fill in the form with the mid-sourcing server URL and the SMS operator created previously on the mid server.
Confirm the connection by clicking on **[!UICONTROL Test the connection]** button.

![](assets/midtab_smsextaccount.png){zoomable="yes"}

1. Click **[!UICONTROL Save]**.

## Create an SMPP external account on the Mid-server {#smpp-external-account-mid}

>[!IMPORTANT]
>
>Using the same account and password for multiple external SMS accounts can result in conflicts and overlap between the accounts. Refer to the SMS troubleshooting page.



## Configure the delivery template {#sms-delivery-template}