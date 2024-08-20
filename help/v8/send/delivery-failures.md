---
title: Delivery failures in Campaign
description: Understand possible failures when sending messages with Adobe Campaign
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
---
# Understand delivery failures {#delivery-failures}

Bounces are the result of a delivery attempt and failure where the ISP provides back failure notices. Bounce handling processing is a critical part of list hygiene. After a given email has bounced several times in a row, this process flags it for suppression.

This process prevents systems from continuing to send invalid email addresses. Bounces are one of the key pieces of data that ISPs use to determine IP reputation. Keeping an eye on this metric is important. "Delivered" versus "bounced" is probably the most common way of measuring the delivery of marketing messages: the higher the delivered percentage is, the better.

If a message cannot be sent to a profile, the remote server automatically sends an error message to Adobe Campaign. This error is qualified to determine whether the email address, phone number or device should be quarantined. See [Bounce mail management](#bounce-mail-qualification).

Once a message is sent, you can view the delivery status for each profile and the associated failure type and reason in the delivery logs.

When an email address is quarantined, or if a profile is on denylist, the recipient is excluded at the delivery preparation step. Excluded messages are listed in the delivery dashboard.

## Why has the message delivery failed {#delivery-failure-reasons}

There are two types of error when a message fails. Each delivery failure type determines if an address is sent to [quarantine](quarantines.md#quarantine-reason) or not.

* **Hard bounces**
  Hard bounces are permanent failures generated after an ISP determines a mailing attempt to a subscriber address as not deliverable. Within Adobe Campaign, hard bounces that are categorized as undeliverable are added to the quarantine list, which means they wouldn't be reattempted. There are some cases where a hard bounce would be ignored if the cause of the failure is unknown.
  
  Here are some common examples of hard bounces: Address doesn't exist, Account disabled, Bad syntax, Bad domain

* **Soft bounces**
  Soft bounces are temporary failures that ISPs generate when they have difficulty delivering mail. Soft failures will [retry](#retries) multiple times (with variance depending on use of custom or out-of-box delivery settings) in order to attempt a successful delivery. Addresses that continually soft bounce will not be added to quarantine until the maximum number of retries has been attempted (which again vary depending on settings). 
  
  Some common causes of soft bounces include the following: Mailbox full, Receiving email server down, Sender reputation issues

The  **Ignored** type of error is known to be temporary, such as "Out of office", or a technical error, for example if the sender type is "postmaster".

The feedback loop operates like bounce emails: when a user qualifies an email as spam, you can configure email rules in Adobe Campaign to block all deliveries to this user. The addresses of these users are denylisted even though they did not click the unsubscription link. Addresses are added to the (**NmsAddress**) quarantine table and not to the (**NmsRecipient**) recipient table with the **[!UICONTROL Denylisted]** status. Learn more about feedback loop mechanism in the [Adobe Deliverability Best Practices Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

A message delivery can fail immediately, in that case we qualify this as a synchronous error. If message sending fails or later on, after it has been sent, the error is asynchronous.

These types of errors are managed as follows:

* **Synchronous error**: the remote server contacted by the Adobe Campaign delivery server immediately returns an error message. The delivery is not allowed to be sent to the profile's server. The Mail Transfer Agent (MTA) determines the bounce type and qualifies the error, and sends back that information to Campaign in order to determine whether the email addresses concerned should be quarantined. See [Bounce mail qualification](#bounce-mail-qualification). 

* **Asynchronous error**: a bounce mail or a SR is resent later by the receiving server. This error is qualified with a label related to the error. Asynchronous errors can occur up until one week after a delivery has been sent.

>[!NOTE]
>
>As a Managed Cloud Services user, configuration of the bounce mailbox is performed by Adobe.

## Bounce mail qualification {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

The way bounce mail qualification is handled in Adobe Campaign depends on the error type:

* **Synchronous errors**: The MTA determines the bounce type and qualification, and sends back that information to Campaign. The bounce qualifications in the **[!UICONTROL Delivery log qualification]** table are not used for **synchronous** delivery failure error messages.

* **Asynchronous errors**: Rules used by Campaign to qualify asynchronous delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. Asynchronous bounces are qualified by the inMail process through the **[!UICONTROL Inbound email]** rules. For more on this, refer to [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]**: the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## Retry management {#retries}

If message delivery fails following a temporary error (**Soft** or **Ignored**), Campaign retries sending. These retries can be performed until the end ot the delivery duration.

Soft bounce retries and the length of time between them are determined by the MTA based on the type and severity of the bounce responses coming back from the message's email domain.

>[!NOTE]
>
>The retry settings in the delivery properties are not used by Campaign.

## Validity period {#valid-period}

The validity period setting in your Campaign deliveries is limited to **3.5 days or less**. For a delivery, if you define a value higher than 3.5 days in Campaign, it will not be taken into account.

For example, if the validity period is set to the default value of 5 days in Campaign, soft-bouncing messages will go into the MTA retry queue and be retried for only up to 3.5 days from when that message reached the MTA. In that case, the value set in Campaign will not be used.

Once a message has been in the MTA queue for 3.5 days and has failed to deliver, it will time out and its status will be updated from **[!UICONTROL Sent]** to **[!UICONTROL Failed]** in the delivery logs.

For more on the validity period, see the [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.


## Email error types {#email-error-types}

For the email channel, possible reasons for a delivery failure are listed below. 

<table> 
 <tbody> 
  <tr> 
   <td> Error label </td> 
   <td> Error type </td> 
   <td> Technical Value </td> 
   <td> Description </td> 
  </tr> 
  <tr> 
   <td> Account disabled </td> 
   <td> Soft / Hard </td> 
   <td> 4 </td> 
   <td> The account linked to the address is not active anymore. When the Internet Access Provider (IAP) detects a lengthy period of inactivity, it can close the user's account. Deliveries to the user's address will then be impossible. If the account is temporarily disabled due to six months of inactivity and can still be activated, the status With errors will be assigned and the account will be tried again until the error counter reaches 5. If the error signals that the account is permanently deactivated, it will directly be set to Quarantine.<br /> </td> 
  </tr> 
  <tr> 
   <td> Address in quarantine </td> 
   <td> Hard </td> 
   <td> 9 </td> 
   <td> The address was placed in quarantine.<br /> </td> 
  </tr> 
  <tr> 
   <td> Address not specified </td> 
   <td> Hard </td> 
   <td> 7 </td> 
   <td> No address is given for the recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bad-quality address </td> 
   <td> Ignored </td> 
   <td> 14 </td> 
   <td> The quality rating for this address is too low.<br /> </td> 
  </tr> 
  <tr> 
   <td> Denylisted address </td> 
   <td> Hard </td> 
   <td> 8 </td> 
   <td> The address was added to the denylist at the time of sending. This status is used for importing data from external lists and external systems into the Adobe Campaign Quarantine list.<br /> </td> 
  </tr> 
  <tr> 
   <td> Control address </td> 
   <td> Ignored </td> 
   <td> 127 </td> 
   <td> The recipient's address is part of the control group.<br /> </td> 
  </tr> 
  <tr> 
   <td> Double </td> 
   <td> Ignored </td> 
   <td> 10 </td> 
   <td> The address of the recipient was already in this delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Error ignored </td> 
   <td> Ignored </td> 
   <td> 25 </td> 
   <td> The address is on the allowlist. The error is therefore ignored and an email will be sent.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluded after arbitration </td> 
   <td> Ignored </td> 
   <td> 12 </td> 
   <td> The recipient was excluded by a 'arbitration' type campaign typology rule.<br /> </td> 
  </tr> 
  <tr> 
   <td> Excluded by a SQL rule </td> 
   <td> Ignored </td> 
   <td> 11 </td> 
   <td> The recipient was excluded by a 'SQL' type campaign typology rule.<br /> </td> 
  </tr> 
  <tr> 
   <td> Invalid domain </td> 
   <td> Soft </td> 
   <td> 2 </td> 
   <td> The domain of the email address is incorrect or no longer exists. This profile will be targeted again until the error count reaches 5. After this, the record will be set to Quarantine status and no retry will follow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mailbox full </td> 
   <td> Soft </td> 
   <td> 5 </td> 
   <td> The mailbox of this user is full and cannot accept more messages. This profile will be targeted again until the error count reaches 5. After this, the record will be set to Quarantine status and no retry will follow.<br /> This type of error is managed by a clean-up process, the address is set to a valid status after 30 days.<br /> Warning: for the address to be automatically removed from the list of quarantined addresses, the Database cleanup technical workflow must be started.<br /> </td> 
  </tr> 
  <tr> 
   <td> Not connected </td> 
   <td> Ignored </td> 
   <td> 6 </td> 
   <td> The recipient's mobile phone is switched off or not connected to the network when the message is sent.<br /> </td> 
  </tr> 
  <tr> 
   <td> Not defined </td> 
   <td> Not defined </td> 
   <td> 0 </td> 
   <td> The address is in qualification because error has not been incremented yet. This type of error occurs when a new error message is sent by the server: it can be an isolated error, but if it occurs again, the error counter increases, which will alert the technical teams. They can then carry out message analysis and qualify this error, via the <span class="uicontrol">Administration</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">Non deliverables Management</span> node in the tree structure.<br /> </td> 
  </tr> 
  <tr> 
   <td> Not eligible for the offers </td> 
   <td> Ignored </td> 
   <td> 16 </td> 
   <td> The recipient was not eligible for the offers in the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Refused </td> 
   <td> Soft / Hard </td> 
   <td> 20 </td> 
   <td> The address has been placed in quarantine due to a security feedback as a spam report. According to the error, the address will be tried again until the error counter reaches 5, or it will be directly sent to quarantines.<br /> </td> 
  </tr> 
  <tr> 
   <td> Target limited in size </td> 
   <td> Ignored </td> 
   <td> 17 </td> 
   <td> The maximum delivery size was reached for the recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unqualified address </td> 
   <td> Ignored </td> 
   <td> 15 </td> 
   <td> The postal address has not been qualified.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unreachable </td> 
   <td> Soft / Hard </td> 
   <td> 3 </td> 
   <td> An error has occurred in the message delivery chain. It could be an incident on the SMTP relay, a domain that is temporarily unreachable, etc. According to the error, the address will be tried again until the error counter reaches 5, or it will be directly sent to quarantines.<br /> </td> 
  </tr> 
  <tr> 
   <td> User unknown </td> 
   <td> Hard </td> 
   <td> 1 </td> 
   <td> The address does not exist. No further deliveries will be attempted for this profile.<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Push notifications error types {#push-error-types}

For the mobile app channel, possible reasons for a delivery failure are listed below. 

### iOS quarantine {#ios-quarantine}

The HTTP/V2 protocol allows a direct feedback and status for each push delivery. If the HTTP/V2 protocol connector is used, the feedback service is no longer called by the **[!UICONTROL mobileAppOptOutMgt]** workflow. A token is considered unregistered when a mobile application is uninstalled or reinstalled.

Synchronously, if the APNs returns an "unregistered" status for a message, the target token will be immediately be put in quarantine.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Error message</strong><br /> </td> 
   <td> <strong>Failure type</strong><br /> </td> 
   <td> <strong>Failure reason</strong><br /> </td> 
   <td> <strong>Retry</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Targeted device powered on<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Targeted device powered off<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> User disables notifications for the application<br /> </td> 
   <td> OK<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Message creation/analysis phase - payload too big<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Payload too long<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Message creation/analysis phase - unexpected content format issue<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Various error messages according to the error<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Undefined<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Certificate issue (password, corruption, etc.) and test connection to APNs issue<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Various error messages according to the error<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Network connection lost during sending<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Connection error<br /> </td> 
   <td> Undefined<br /> </td> 
   <td> Unreachable<br /> </td> 
   <td> Yes<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs message rejection: Unregistration<br /> the user has removed the application or the token has expired<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Unregistered<br /> </td> 
   <td> Hard<br /> </td> 
   <td> User unknown<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs message rejection: all other errors<br /> </td> 
   <td> Failure<br /> </td> 
   <td> The error rejection cause will be present in the error message<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Android quarantine {#android-quarantine}

**For Android V1**

For each notification, Adobe Campaign receives the synchronous errors directly from the FCM server. Adobe Campaign handles them on the fly and generates hard or soft errors according to the severity of the error and retries can be performed:

* Payload length exceeded, connection issue, service availability issue: retry performed, soft error, failure reason is **[!UICONTROL Refused]**.
* Device quota exceeded: no retry, soft error, failure reason is **[!UICONTROL Refused]**.
* Invalid or unregistered token, unexpected error, sender account issue: no retry, hard error, failure reason is **[!UICONTROL Refused]**.

The **[!UICONTROL mobileAppOptOutMgt]** workflow runs every 6 hours to update the **AppSubscriptionRcp** table. For the tokens declared unregistered or no longer valid, the field **Disabled** is set to **True** and the subscription linked to that device token will be automatically excluded from future deliveries.

During the delivery analysis, all the devices that are excluded from the target are automatically added to the **excludeLogAppSubRcp** table.

>[!NOTE]
>
>For customers using the Baidu connector, here are the different types of errors:  
>
>* Connection issue at the beginning of the delivery: failure type **[!UICONTROL Undefined]**, failure reason **[!UICONTROL Unreachable]**, retry is performed.
>* Connection lost during a delivery: soft error, failure reason **[!UICONTROL Refused]**, retry is performed.
>* Synchronous error returned by Baidu during the sending: hard error, failure reason **[!UICONTROL Refused]**, no retry is performed.
>
>Adobe Campaign contacts the Baidu server every 10 minutes to retrieve the sent message's status, and updates the broadlogs. If a message is declared as sent, the status of the message in the broadlogs is set to **[!UICONTROL Received]**. If Baidu declares an error, the status is set to **[!UICONTROL Failed]**.

**For Android V2**

The Android V2 quarantine mechanism uses the same process as Android V1, the same applies to the subscriptions and exclusions update. For more on this refer to the [Android V1](#android-quarantine) section.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Error message</strong><br /> </td> 
   <td> <strong>Failure type</strong><br /> </td> 
   <td> <strong>Failure reason</strong><br /> </td> 
   <td> <strong>Retry</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Message creation/analysis phase: illegal keywords used in the custom fields<br /> </td> 
   <td> Failure<br /> </td> 
   <td> The following keywords cannot be used: {1}<br /> </td> 
   <td> Soft<br /> </td> 
   <td> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Message creation/analysis phase: payload too big<br /> </td> 
   <td> Failure<br /> </td> 
   <td> The notification is too heavy: {1} bits, while only {2} are authorized<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> Network connection lost during sending<br /> </td> 
   <td> Failure<br /> </td> 
   <td> No response from the Firebase Cloud Messaging service on the address: {1}<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Unreachable<br /> </td> 
   <td> Yes<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM message rejection: The FCM server is temporarily unavailable (for example with timeouts). <br /> </td> 
   <td> Failure<br /> </td> 
   <td> The Firebase Cloud Messaging service is temporarily unavailable<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Unreachable<br /> </td> 
   <td> Yes<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM message rejection: Error authenticating the sender account<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Failed to identify the developer account, please check your ID and password<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM message rejection: Device quota exceeded<br /> </td> 
   <td> Failure<br /> </td> 
   <td> </td> 
   <td> Soft<br /> </td> 
   <td> Refused<br /> </td> 
   <td> Yes<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM message rejection: Invalid registration / not registered<br /> </td> 
   <td> Failure<br /> </td> 
   <td> </td> 
   <td> Hard<br /> </td> 
   <td> User unknown<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM message rejection: All other error<br /> </td> 
   <td> Failure<br /> </td> 
   <td> The Firebase Cloud Messaging server has returned an unexpected error code: {1} </td> 
   <td> </td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr> 
    <tr> 
   <td> FCM message rejection: Invalid argument<br /> </td> 
   <td> Failure<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> Ignored</td> 
   <td> Undefined<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: Third party authentication error<br /> </td> 
   <td> Failure<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> Ignored</td>
   <td> Refused<br /> </td> 
   <td> Yes<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: Sender ID mismatch<br /> </td> 
   <td> Failure<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> Soft</td>
   <td> User unknown<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: Unregistered<br /> </td> 
   <td> Failure<br /> </td>
   <td> UNREGISTERED </td> 
   <td> Hard</td> 
   <td> User unknown<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: Internal<br /> </td> 
   <td> Failure<br /> </td> 
   <td> INTERNAL </td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> Yes<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: Unavailable<br /> </td> 
   <td> Failure<br /> </td> 
   <td> UNAVAILABLE</td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> Yes<br /> </td> 
  </tr>
    <tr> 
   <td> FCM message rejection: unexpected error code<br /> </td> 
   <td> Failure<br /> </td> 
   <td> unexpected error code</td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
  <tr> 
   <td> Authentication: Connection issue<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Impossible to connect to authentication server </td> 
   <td> Ignored</td>
   <td> Refused<br /> </td> 
   <td> Yes<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Unauthorized client or scope in request.<br /> </td> 
   <td> Failure<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignored</td>
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Client is unauthorized to retrieve access tokens using this method, or client not authorized for any of the scopes requested.<br /> </td> 
   <td> Failure<br /> </td> 
   <td> unauthorized_client </td> 
   <td> Ignored</td>
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Access denied<br /> </td> 
   <td> Failure<br /> </td>
   <td> access_denied</td> 
   <td> Ignored</td>
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Non-valid email<br /> </td> 
   <td> Failure<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Invalid JWT<br /> </td> 
   <td> Failure<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Invalid JWT Signature<br /> </td> 
   <td> Failure<br /> </td> 
   <td> invalid_grant </td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: Invalid OAuth scope or ID token audience provided<br /> </td> 
   <td> Failure<br /> </td> 
   <td> unauthorized_client</td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
    <tr> 
   <td> Authentication: OAuth client disabled<br /> </td> 
   <td> Failure<br /> </td> 
   <td> disabled_client</td> 
   <td> Ignored</td> 
   <td> Refused<br /> </td> 
   <td> No<br /> </td> 
  </tr>
 </tbody> 
</table>

## SMS quarantines {#sms-quarantines}

**For standard connectors**

The specificities for SMS channel are listed below.

>[!NOTE]
>
>The **[!UICONTROL Delivery log qualification]** table does not apply to the **Extended generic SMPP** connector.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Scenario</strong><br /> </td> 
   <td> <strong>Status</strong><br /> </td> 
   <td> <strong>Error message</strong><br /> </td> 
   <td> <strong>Failure type</strong><br /> </td> 
   <td> <strong>Failure reason</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Sent to the provider<br /> </td> 
   <td> Sent<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Received on the mobile<br /> </td> 
   <td> Received<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Error returned by the provider<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Error while receiving data (SR or MO)<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Unreachable<br /> </td> 
  </tr> 
  <tr> 
   <td> Invalid MT acknowledge<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Error '{1}' while processing acknowledgment frame for send query<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Unreachable<br /> </td> 
  </tr> 
  <tr> 
   <td> Error while sending the MT<br /> </td> 
   <td> Failure<br /> </td> 
   <td> Error while sending messages<br /> </td> 
   <td> Soft<br /> </td> 
   <td> Unreachable<br /> </td> 
  </tr> 
 </tbody> 
</table>

**For the Extended generic SMPP connector**

When using the SMPP protocol to send SMS messages, the error management is handled differently.

The SMPP connector retrieves data from the SR (Status Report) message that is returned using regular expressions (regexes) to filter its content. This data is then matched against the information found in the **[!UICONTROL Delivery log qualification]** table (available via the **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** menu).

Before a new type of error is qualified, the failure reason is always set to **Refused** by default.

>[!NOTE]
>
>The failure types and reasons for failure are the same as for emails.
>
>Ask your provider for a list of status and error codes in order to set proper failure types and reasons for failure in the Delivery log qualification table.

Example of a generated message:

```
SR Generic DELIVRD 000|#MESSAGE#
```

* All error messages begin with **SR** to distinguish SMS error codes from email error codes.
* The second part (**Generic** in this example) of the error message refers to the name of the SMSC implementation such as defined in the **[!UICONTROL SMSC implementation name]** field of the SMS external account.

  Because the same error code may have a different meaning for each provider, this field allows you to know which provider generated the error code. You can then find the error in the relevant provider's documentation.

* The third part (**DELIVRD** in this example) of the error message corresponds to the status code retrieved from the SR using the status extraction regex defined in the SMS external account.

  This regex is specified in the **[!UICONTROL SMSC specificities]** tab of the external account.
  By default, the regex extracts the **stat:** field as defined by the **Appendix B** section of the **SMPP 3.4 specification**.

* The fourth part (**000** in this example) of the error message corresponds to the error code extracted from the SR using the error code extraction regex defined in the SMS external account.

  This regex is specified in the **[!UICONTROL SMSC specificities]** tab of the external account.

  By default, the regex extracts the **err:** field as defined by the **Appendix B** section of the **SMPP 3.4 specification**.

* Everything that comes after the pipe symbol (|) is only displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Delivery log qualification]** table. This content is always replaced by **#MESSAGE#** after the message is normalized. This process avoids having multiple entries for similar errors and is the same as for emails.

The Extended generic SMPP connector applies a heuristic to find sensible default values: if the status begins with **DELIV**, it is considered a success because it matches the common statuses **DELIVRD** or **DELIVERED** used by most providers. Any other status leads to a hard failure.
