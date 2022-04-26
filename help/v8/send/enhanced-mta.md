---
product: Campaign
title: Send with the Enhanced MTA in Adobe Campaign
description: Learn about the scope and the specificities of sending emails with the Adobe Campaign Enhanced MTA
feature: Email
role: Data Engineer
level: Beginner

---
# Sending with the Enhanced MTA {#sending-with-enhanced-mta}

The **Adobe Campaign Enhanced MTA** (Mail Transfer Agent) provides an upgraded sending infrastructure allowing for optimal deliverability, reputation, throughput, reporting, bounce handling, IP ramp up and connection setting management.

It is implemented to improve scalability, increase delivery throughput and help send more emails faster. This is achieved with new adaptive delivery techniques that alter email sending settings in real-time based on feedback from Internet Service Providers.

## Usage and benefits

**What is the Enhanced MTA?**

Adobe Campaign uses a Mail Transfer Agent (MTA) which runs SparkPost’s commercial email MTA called **Momentum**.

Momentum represents innovative, high-performance MTA technology which includes smarter bounce handling and an automated deliverability optimization capability that helps senders achieve and maintain optimal inbox delivery rates.

**What are the benefits?**

* The Enhanced MTA allows a massive increase in overall throughput speed and a significant reduction in soft bounces.
* It uses the latest MTA technology to provide you with the optimal throughput speeds for your email delivery.
* By adapting instantly and automatically to the feedback it receives, it also ensures more accurate and intelligent email delivery with real-time delivery data.

## Enhanced MTA specificities {#enhanced-mta-impacts}

### Bounce qualification

For **synchronous** delivery failure error messages, the Enhanced MTA determines the bounce type and qualification, and sends back that information to Campaign.

The Enhanced MTA qualifies the SMTP bounce and sends that qualification back to Campaign in the form of a bounce code mapped to a Campaign bounce reason and qualification.

>[!NOTE]
>
>Currently **asynchronous** bounces are qualified by the inMail process through the **[!UICONTROL Inbound email]** rules. For more on this, refer to [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Learn more on delivery failures in [this section](delivery-failures.md).

### Validity period

The validity period setting in your Campaign deliveries will be used by the Enhanced MTA only if set to **3.5 days or less**. If you define a value higher than 3.5 days in Campaign, it will not be taken into account.

For example, if the validity period is set to the default value of 5 days in Campaign, soft-bouncing messages will go into the Enhanced MTA retry queue and be retried for only up to 3.5 days from when that message reached the Enhanced MTA. In that case, the value set in Campaign will not be used.

Once a message has been in the Enhanced MTA queue for 3.5 days and has failed to deliver, it will time out and its status will be updated from **[!UICONTROL Sent]** to **[!UICONTROL Failed]** in the delivery logs.

For more on the validity period, see the [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.

### Retries

Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message’s email domain.

>[!NOTE]
>
>The retry settings in the delivery properties are not used by Campaign.

Learn more on retries in [this section](delivery-failures.md#retries).

### Specific MX rules

MX rules (Mail eXchanger) are the rules that manage communication between a sending server and a receiving server.

The Enhanced MTA has its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you’re sending emails.

### DKIM-signing

Domain Keys Identified Mail (DKIM) is an authentication method that is used to detect forged sender addresses (commonly called spoofing). 

In Adobe Campaign, DKIM email authentication signing is performed by the Enhanced MTA.

Lern more on DKIM in the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication){target="_blank"}.

## Email Feedback Service {#email-feedback-service}

With the Email Feedback Service (EFS) capability, the status of each email is accurately reported, because feedback is captured directly from the Enhanced MTA (Message Transfer Agent).

Once the delivery has started, there is no change in the **[!UICONTROL Success]** percentage when the message is successfully relayed from Campaign to the Enhanced MTA.

The delivery logs show the **[!UICONTROL Taken into account by the service provider]** status for each targeted address.

When the message is actually delivered to the targeted profiles and once this information is reported back in real time from the Enhanced MTA, the delivery logs show the **[!UICONTROL Sent]** status for each address that successfully received the message. The **[!UICONTROL Success]** percentage is increased accordingly with each successful delivery.

When hard-bouncing messages get reported back from the Enhanced MTA, their log status changes from **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

When soft-bouncing messages get reported back from the Enhanced MTA, their log status remains unchanged (**[!UICONTROL Taken into account by the service provider]**): only the [error reason](delivery-failures.md#delivery-failure-reasons) is updated<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. The **[!UICONTROL Success]** percentage remains unchanged. Soft-bouncing messages are then retried throughout the delivery [validity period](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}:

* If a retry is successful before the end of the validity period, the message status changes to **[!UICONTROL Sent]** and the **[!UICONTROL Success]** percentage is increased accordingly.

* Otherwise, the status changes to **[!UICONTROL Failed]**. The **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->percentage remains unchanged.
  
>[!NOTE]
>
>For more on hard and soft bounces, see [this section](delivery-failures.md#delivery-failure-reasons).
>
>For more on retries after a delivery temporary failure, see [this section](delivery-failures.md#retries).

The table below shows how the KPIs and sending logs statuses are updated at each step of the sending process with the EFS capability.

| Step in the sending process  | KPI summary | Sending logs status |
|--- |--- |--- |
| Message is successfully relayed from Campaign to the Enhanced MTA | **[!UICONTROL Success]** percentage is not displayed (starts out at 0%) | Taken into account by the service provider |
| Hard-bouncing messages get reported back from the Enhanced MTA | No change in **[!UICONTROL Success]** percentage | Failed |
| Soft-bouncing messages get reported back from the Enhanced MTA | No change in **[!UICONTROL Success]** percentage | Taken into account by the service provider |
| Soft-bouncing messages retries are successful | **[!UICONTROL Success]** percentage is increased accordingly | Sent |
| Soft-bouncing messages retries fail |  No change in **[!UICONTROL Success]** percentage  | Failed |

