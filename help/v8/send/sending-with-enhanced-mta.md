---
product: Campaign
title: Send with the Enhanced MTA in Adobe Campaign Classic
description: Learn about the scope and the specificities of sending emails with the Adobe Campaign Enhanced MTA
feature: Email

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

### New MX rules

MX rules (Mail eXchanger) are the rules that manage communication between a sending server and a receiving server.

The Enhanced MTA has its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you’re sending emails.

### Bounce qualification

For **synchronous** delivery failure error messages, the Enhanced MTA determines the bounce type and qualification, and sends back that information to Campaign.

>[!NOTE]
>
>Asynchronous bounces are qualified by the inMail process through the **[!UICONTROL Inbound email]** rules. For more on this, refer to [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

The Enhanced MTA qualifies the SMTP bounce and sends that qualification back to Campaign in the form of a bounce code mapped to a Campaign bounce reason and qualification.

Learn more on delivery failures in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target="_blank"}

### Validity period

The validity period setting in your Campaign deliveries will be used by the Enhanced MTA only if set to **3.5 days or less**. If you define a value higher than 3.5 days in Campaign, it will not be taken into account.

For example, if the validity period is set to the default value of 5 days in Campaign, soft-bouncing messages will go into the Enhanced MTA retry queue and be retried for only up to 3.5 days from when that message reached the Enhanced MTA. In that case, the value set in Campaign will not be used.

Once a message has been in the Enhanced MTA queue for 3.5 days and has failed to deliver, it will time out and its status will be updated from **[!UICONTROL Sent]** to **[!UICONTROL Failed]** in the delivery logs.

For more on the validity period, see [this section](steps-sending-the-delivery.md#defining-validity-period).

### DKIM-signing

DKIM (DomainKeys Identified Mail) email authentication signing is done by the Enhanced MTA. DKIM-signing by the native Campaign MTA will be turned off within the Domain management table as part of the Enhanced MTA upgrade.
For more on DKIM, see the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).

### Email Feedback Service {#email-feedback-service}

With the Email Feedback Service (EFS) capability, the status of each email is accurately reported, because feedback is captured directly from the Enhanced MTA (Message Transfer Agent).

>[!IMPORTANT]
>
>The Email Feedback Service is currently available as a beta capability.
>
>If you’re interested in participating in this beta program, fill out [this form](https://forms.office.com/Pages/ResponsePage.aspx?id=Wht7-jR7h0OUrtLBeN7O4Rol2vQGupxItW9_BerXV6VUQTJPN1Q5WUI4OFNTWkYzQjg3WllUSDAxWi4u) and we’ll get back to you.

Once the delivery has started, there is no change in the **[!UICONTROL Success]** percentage when the message is successfully relayed from Campaign to the Enhanced MTA.

<!--![](assets/efs-sending.png)-->

The delivery logs show the **[!UICONTROL Taken into account by the service provider]** status for each targeted address.

<!--![](assets/efs-pending.png)-->

When the message is actually delivered to the targeted profiles and once this information is reported back in real time from the Enhanced MTA, the delivery logs show the **[!UICONTROL Sent]** status for each address that successfully received the message. The **[!UICONTROL Success]** percentage is increased accordingly with each successful delivery.

When hard-bouncing messages get reported back from the Enhanced MTA, their log status changes from **[!UICONTROL Taken into account by the service provider]** to **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

When soft-bouncing messages get reported back from the Enhanced MTA, their log status remains unchanged (**[!UICONTROL Taken into account by the service provider]**): only the [error reason](understanding-delivery-failures.md#delivery-failure-types-and-reasons) is updated<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. The **[!UICONTROL Success]** percentage remains unchanged. Soft-bouncing messages are then retried throughout the delivery [validity period](steps-sending-the-delivery.md#defining-validity-period):

* If a retry is successful before the end of the validity period, the message status changes to **[!UICONTROL Sent]** and the **[!UICONTROL Success]** percentage is increased accordingly.

* Otherwise, the status changes to **[!UICONTROL Failed]**. The **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->percentage remains unchanged.
  
>[!NOTE]
>
>For more on hard and soft bounces, see [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#delivery-failure-types-and-reasons){target="_blank"}.
>
>For more on retries after a delivery temporary failure, see [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#retries-after-a-delivery-temporary-failure){target="_blank"}.

The table below shows the KPIs and sending logs statuses (with the EFS capability).

**With Email Feedback Service**

| Step in the sending process  | KPI summary | Sending logs status |
|--- |--- |--- |
| Message is successfully relayed from Campaign to the Enhanced MTA | **[!UICONTROL Success]** percentage is not displayed (starts out at 0%) | Taken into account by the service provider |
| Hard-bouncing messages get reported back from the Enhanced MTA | No change in **[!UICONTROL Success]** percentage | Failed |
| Soft-bouncing messages get reported back from the Enhanced MTA | No change in **[!UICONTROL Success]** percentage | Taken into account by the service provider |
| Soft-bouncing messages retries are successful | **[!UICONTROL Success]** percentage is increased accordingly | Sent |
| Soft-bouncing messages retries fail |  No change in **[!UICONTROL Success]** percentage  | Failed |

