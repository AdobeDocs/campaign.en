---
title: Monitor and track a SMS
description: About the monitoring and tracking of an SMS delivery
feature: SMS
role: User
level: Beginner, Intermediate
---

# Monitor and track a SMS

It is important to monitor you SMS delivery, in order to be sure that your marketing campaigns are efficient.

Here the possibilities you have to know what happens after the sending of your delivery

## Understand the SMS delivery dashboad

The delivery dashboard gives you many information about your SMS. 

To access the dashboard, double-click on your delivery in the delivery list.

In the **[!UICONTROL Summary]** tab, you have the main data like the number of messages processed, and the number of success.

![](assets/sms_summary.png){zoomable="yes"}

After the sending of the SMS, the **[!UICONTROL SMS]** tab, which is about the content of the delivery, is no longer accessible for a change.

In the **[!UICONTROL Delivery]** tab, you have the information about the delivery logs. For each address contacted, you can see if the SMS has been sent or not

![](assets/sms_deliverylogs.png){zoomable="yes"}

You can see in the **[!UICONTROL Exclusions]** tab the details on why some addresses are excluded from the target.

![](assets/sms_exclusions.png){zoomable="yes"}

The **[!UICONTROL Tracking]** tab is about the tracking. Below the example of an URL tracked in the SMS content.

![](assets/sms_trackinglogs.png){zoomable="yes"}

And last, the **[!UICONTROL Audit]** tab with all the details during the launch of the delivery :

![](assets/sms_audit.png){zoomable="yes"}

## Understand SMS failures

The failure types and reasons for failure for SMS are the same as for emails.

Learn more about [delivery failures](../delivery-failures.md) and specifically about [SMS quarantines](../delivery-failures.md#sms-quarantines).

## Process inbound messages

The **[!UICONTROL nlserver sms]** module queries the SMS router at regular intervals. This allows Adobe Campaign to track the progress of deliveries and handle the status reports and recipient unsubscription requests.

* **Status reports** : view delivery logs to check the status of your messages.

>[!IMPORTANT]
>
>Every SMS sent is linked to an external account its primary key. In this way:
Status reports from a deleted external SMS account are not correctly processed.
An SMS account can only be linked to a single external account to ensure that status reports are attributed to the correct account

* **Unsubscription** : recipients who wish to stop receiving SMS deliveries can return a message containing the word STOP. If your provider allows it under the terms of the contract, you can retrieve messages via the **[!UICONTROL Inbound SMS]** workflow activity and then create a query to enable the **[!UICONTROL No longer contact this recipient]** option for the recipients concerned.

Learn more about the [Inbound SMS activity](../../../automation/workflow/inbound-sms.md)

## InSMS schema

The **[!UICONTROL InSMS schema]** contains information relevant to incoming SMS. A description of these fields is available via the desc attribute.

* **message**: content of the SMS received.

* **origin**: mobile number at the origin of message.

* **providerId**: identifier of the message returned by the SMSC (message center).

* **created**: date incoming message was inserted into Adobe Campaign.

* **extAccount**: Adobe Campaign external account.

>[!IMPORTANT]
>
>The following fields are specific to NetSize.
If the operator in use is not NetSize, these fields are considered empty.

* **alias**: alias of incoming message.

* **separator**: separator between the alias and the body of the message.

* **messageDate**: message date given by operator.

* **receivalDate**: date message from operator was received by SMSC (message center).

* **deliveryDate**: date message sent by SMSC (message center).

* **largeAccount**: customer account code linked to incoming SMS.

* **countryCode**: operator country code.

* **operatorCode**: operator network code.

* **linkedSmsId** : Adobe Campaign identifier (broadlogId) linked to outgoing SMS, where this SMS is the response.
