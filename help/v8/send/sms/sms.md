---
title: Send SMS with Adobe Campaign
description: Get started with SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
---
# Get started with SMS {#gs-sms-channel}

Use Adobe Campaign to send text messages to your customers on their mobile devices. You can create, personalize, and preview messages in text format from the SMS editor.

To deliver SMS to mobile devices with Adobe Campaign, you need:

* An external account configured on the **[!UICONTROL Mobile (SMS)]** channel. Learn how to configure the SMS channel on your [mid-sourcing infrastructure](sms-mid-sourcing.md). For this configuration, you need to understand the [SMPP external account parameters](smpp-external-account.md) and the [SMS channel characteristics](sms-channel.md).
    After this set up, check your SMPP connection and know how to troubleshoot it if needed. [Learn more](smpp-connection.md).

* An SMS delivery template that is correctly linked to this external account.


>[!NOTE]
>
>You can also use Adobe Campaign to send [push notifications](../push.md) and [LINE](../line/line.md) messages to mobile devices.
>
> For customers using the legacy SMS connector, the existing implementation remains supported. However, we recommend moving to the new connector. Contact Adobe if you would like to transition.

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Create SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Create a SMS delivery</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="SMS content" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>Define your SMS content</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="SMS audience" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Select the audience</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="SMS configuration" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configure SMS channel</strong></a>
</div>
<p>
</td>
</tr></table>
