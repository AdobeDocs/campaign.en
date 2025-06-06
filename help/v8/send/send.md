---
title: Send and monitor your emails
description: Learn about the scope and the specificities of sending emails with Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
---

# Send and monitor your emails  {#send-and-monitor-emails}

When the delivery is configured and ready to be sent, make sure you have run the delivery analysis. [Learn more](delivery-analysis.md)

Once done, confirm the delivery to launch the delivery of messages.

Track the execution of the delivery from the **Delivery** tab, accessible via the detail of this delivery or via the list of deliveries.

## Monitor your emails {#email-monitoring}

Once sent, check your delivery status in the **Delivery Dashboard** and access delivery logs and reports to confirm messages were correctly sent.

From the delivery dashboard, you can check the processed messages and delivery audit logs. You can also control the status of the messages in the delivery logs.

>[!NOTE]
>
>Delivery statuses are not displayed in real-time. Learn more about Email Feedback Service [in this section](#email-feedback-service).


[Learn more about delivery monitoring in Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}

## Campaign MTA {#mta}

Campaign v8 Mail Transfer Agent (MTA) provides a best-in-class sending infrastructure allowing for optimal deliverability, reputation, throughput, reporting, bounce handling, IP ramp up and connection setting management.

Available for all Campaign v8 customers, it guarantees scalability, a high delivery throughput and helps send more emails faster. This is achieved with new adaptive delivery techniques that alter email sending settings in real-time based on feedback from Internet Service Providers.

### Benefits

Adobe Campaign uses a Mail Transfer Agent (MTA) which runs SparkPost's commercial email MTA called **Momentum**.

Momentum represents innovative, high-performance MTA technology which includes smarter bounce handling and an automated deliverability optimization capability that helps senders achieve and maintain optimal inbox delivery rates.

* The MTA allows a massive increase in overall throughput speed and a significant reduction in soft bounces.
* It uses the latest MTA technology to provide you with the optimal throughput speeds for your email delivery.
* By adapting instantly and automatically to the feedback it receives, it also ensures more accurate and intelligent email delivery with real-time delivery data.

### Bounce qualification

For **synchronous** delivery failure error messages, the MTA determines the bounce type and qualification, and sends back that information to Campaign.

The MTA qualifies the SMTP bounce and sends that qualification back to Campaign in the form of a bounce code mapped to a Campaign bounce reason and qualification.

>[!NOTE]
>
>Currently **asynchronous** bounces are qualified by the inMail process through the **[!UICONTROL Inbound email]** rules. 

Learn more on delivery failures in [this section](delivery-failures.md).


### Specific MX rules

MX rules (Mail eXchanger) are the rules that manage communication between a sending server and a receiving server.

The MTA has its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you're sending emails.

### DKIM-signing

Domain Keys Identified Mail (DKIM) is an authentication method that is used to detect forged sender addresses (commonly called spoofing). 

In Adobe Campaign, DKIM email authentication signing is performed by the MTA.

Lern more on DKIM in the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## Email Feedback Service {#email-feedback-service}

Campaign Email Feedback Service (EFS) reports the status of each email delivery send with Adobe Campaign.

Once the delivery has started, there is no change in the **[!UICONTROL Success]** percentage when the message is successfully relayed from Campaign to the MTA. The delivery logs show the **[!UICONTROL Taken into account by the service provider]** status for each targeted address.

When the message is actually delivered to the targeted profiles and once this information is reported back in real time from the MTA, the delivery logs show the **[!UICONTROL Sent]** status for each address that successfully received the message. The **[!UICONTROL Success]** percentage is increased accordingly with each successful delivery.

When hard-bouncing messages get reported back from the MTA, their log status changes from **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

When soft-bouncing messages get reported back from the MTA, their log status remains unchanged (**[!UICONTROL Taken into account by the service provider]**): only the [error reason](delivery-failures.md#delivery-failure-reasons) is updated<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. The **[!UICONTROL Success]** percentage remains unchanged. Soft-bouncing messages are then retried throughout the delivery [validity period](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* If a retry is successful before the end of the validity period, the message status changes to **[!UICONTROL Sent]** and the **[!UICONTROL Success]** percentage is increased accordingly.

* Otherwise, the status changes to **[!UICONTROL Failed]**. The **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->percentage remains unchanged.
  
>[!NOTE]
>
>For more on hard and soft bounces, see [this section](delivery-failures.md#delivery-failure-reasons).
>
>For more on retries after a delivery temporary failure, see [this section](delivery-failures.md#retries).

The table below shows how the KPIs and sending logs statuses are updated at each step of the sending process.

| Step in the sending process  | KPI summary | Sending logs status |
|--- |--- |--- |
| Message is successfully relayed from Campaign to the MTA | **[!UICONTROL Success]** percentage is not displayed (starts out at 0%) | Taken into account by the service provider |
| Hard-bouncing messages get reported back from the MTA | No change in **[!UICONTROL Success]** percentage | Failed |
| Soft-bouncing messages get reported back from the MTA | No change in **[!UICONTROL Success]** percentage | Taken into account by the service provider |
| Soft-bouncing messages retries are successful | **[!UICONTROL Success]** percentage is increased accordingly | Sent |
| Soft-bouncing messages retries fail |  No change in **[!UICONTROL Success]** percentage  | Failed |
