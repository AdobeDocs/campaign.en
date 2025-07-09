---
title: Validating a SMPP connection
description: Learn how to validate a SMPP connection
feature: SMS
role: User
level: Intermediate
exl-id: eda6934a-e48a-4932-8c88-588f661005d6
---
# Validating a SMPP connection {#validate-smpp-connection}

Here are some checks to do be sure your SMPP connection is OK.

## Things to check before going live {#check-go-live}

Before going live, be sure your SMPP setup is Ok with the list of checks below.

>[!IMPORTANT]
>
>This checklist is not exhaustive. The more checks you do, the better.

>[!NOTE]
>
>Enable verbose SMPP traces during checks, it will help you and the support team to understand the troubleshoutings.

### Check for external account conflicts {#sms-external-accounts-check}

Check that you don't have leftover SMS external accounts. Delete the test accounts in order to eliminate potential conflicts.

Check that no other instance connect to the external account. In particular, make sure that the preprod environment does not connect to the prod external account.

If you need to have multiple accounts on the same Campaign instance that connect to the same provider, contact the provider to make sure that they actually distinguish connections between these accounts. Having multiple accounts with the same login requires extra configuration.

Check that all enabled SMS external accounts have the dedicated process setting enabled. You cannot mix between the 2 kinds of accounts (with and without dedicated process) on the same instance.

### Do a real-world test {#real-test}

Try sending a few SMS on different mobiles.

**Send SMS with all kinds of characters**

If you need to send SMS with non-GSM or non-ASCII characters, try sending some messages with the most diverse characters as possible. If you set up a custom character mapping table, send at least one SMS for all possible data_coding values.

**Check that SR are properly processed**

The SMS should be marked as received in the delivery log. The delivery log should be successful and look like this: "*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*".

Check that you properly set the "*SMSC Implementation name*" field: the delivery log must never contain "*SR Generic*" on production environments.

**Check that MO are processed**

Send a few SMS for all automatic reply keywords and check that the reply is quick (no more than a few seconds).

Check that MOs are inserted into the *nms:inSms* database. If you have custom TLVs, make sure they are also inserted correctly and properly formatted.

Check in the log that Campaign replies with a successful *DELIVER_SM_RESP (command_status=0)*.

**Do a load test**

This is especially important if you send a lot of messages or if you use real-time messaging.

Do a test that will load the connection at 100% for at least 5 seconds. You will have to send real messages if the provider doesn't have a way to connect to a fake account for tests. A way to achieve that is to monitor closely the first big enough delivery with verbose SMPP messages enabled.

The minimum number of messages to send could be calculated like this:

*Max MT throughput * Total number of transmitter/transceiver connections * 5*

After the delivery is finished, check the following things:

* Check that all messages were sent (not necessarily received)
* There must be absolutely zero PDU with command_status not 0x00000000, unless this is explicitely stated by the provider as normal operation
* Connections must stay absolutely stable (no BIND PDU) during the whole delivery process.
* Check that all messages have a SR and that it was correctly processed (see [Check that SR are properly processed](#real-test)). If a small percentage has errors, check that these were actual SR returning errors, not errors during sending or processing on the Campaign side.
* If you are unsure about performance, check that latency is reasonable, especially between a PDU and its corresponding RESP, having more than 500ms latency can be a problem for high throughput. Use that latency to check the sending window formula (see the Sending window setting for more details)

### Check PDUs {#pdu}

Check that PDUs are properly formatted.

>[!IMPORTANT]
>
>This step is strongly recommended when connecting to a provider that was not connected to Campaign before.

**BIND**

Check that BIND_* PDUs are correctly sent. The most important thing to check is that the provider always returns successful BIND_*_RESP PDUs (command_status = 0).

Check that there aren't too many BIND_* PDUs. If there are too many of them, it might indicate that the connection is unstable. See the Issues with unstable connections troubleshooting section below for more information about that.

**ENQUIRE_LINK**

Check that ENQUIRE_LINK PDUs are regularly exchanged when the connection is idle.

**SUBMIT_SM / DELIVER_SM**

Send a message, then search in the logs for its corresponding SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM and DELIVER_SM_RESP PDUs.

With the *SUBMIT_SM PDU*:

* Check that data_coding is correct (0 by default).
* Check that short_message is properly encoded: try to decode it using a hexadecimal converter that supports multiple encodings (there are some available online).
* If you use message_payload for long messages, check that the content is present in the optional field and not in the short_message field.

With the *SUBMIT_SM_RESP PDU*:

* Check that it was successful (command_status = 0).
* Check that its body contains a properly formatted ID followed by a '0' byte.

With the *DELIVER_SM PDU*:

* Decode the hexadecimal short_message field (there are online tools for that).
* Check with a regex checking tool that the regex defined in Extraction regex of the ID in the SR returns exactly one capture group and that it captures the whole ID in the message.
* Check that the extracted ID matches the one in SUBMIT_SM_RESP.
* Check that the regex defined in Extraction regex of the status in the SR returns the content of the stat field.
* Check that the regex defined in Extraction regex of the error in the SR returns the content of the err field.

With the *DELIVER_SM_RESP PDU*:

* Check that it was sent quickly after receiving the DELIVER_SM PDU (typically less than 1 second).
* Check that it was successful (command_status = 0).

### Live test with the provider {#sms-live-test}

A best practice before going live is to do a live test with the provider, with both sides looking at logs during the execution.

>[!IMPORTANT]
>
>This step is strongly recommended when connecting to a provider that was never connected to Campaign before.

### Disable verbose SMPP traces {#sms-disable-smpp}

Once all checks are complete, the last action to do is to disable verbose SMPP traces so it doesn't generate too many logs.

## SMS Troubleshooting {#sms-troubleshooting}

### General troubleshooting procedure {#sms-general-troubleshooting}

The SMS connector involves 3 entities: the SMPP provider, Adobe and you. 
The main SMS expert is the SMPP provider, so they should be involved for all SMS traffic-related issues (connection issues, lost messages, encoding problems, country-specific rules, ...).

#### Enable dedicated process {#sms-dedicated-process}

>[!IMPORTANT]
>
>Make sure  **[!UICONTROL Send messages through a dedicated process]** is enabled in all active SMS accounts. 

If you have issues with the older (MTA-based) connector (dedicated process disabled), you should consider migrating to the dedicated process connector. It performs much better, is more stable, and provides much better feedback in its logs.

#### Conflict between different external accounts {#sms-conflict-external-accounts}

If the instance has multiple SMS external accounts, check that problems are not caused by a conflict between accounts.

To isolate the external account causing problems:

1. Disable all external accounts
1. Enable one external account
1. Try to reproduce the problem
1. If the problem does not appear with that single account, disable it and restart to step 2 on the next account. Once you checked every accounts individually, there are 2 possible scenarios:

**The problem appeared on one or several accounts**

In this case, you can apply other troubleshooting procedures on each account individually. It is best to disable other accounts while diagnosing an account, in order to reduce network traffic and the amount of logs.

**The problem did not appear when only one account is active at any time**

You have a conflict between accounts. Adobe Campaign treats accounts individually, but the provider may treat them as a single account.

*You are using different login/password combinations between all your accounts*
You will have to contact the provider to diagnose for potential conflicts on their side.

*Some of the external accounts share the same login/password combination*
The provider has no way to tell from which external account the BIND PDU is coming from, so they treat all connections from the multiple accounts as a single one, so they probably route MO and SR randomly over the 2 accounts, causing seemingly random issues.

If the provider supports multiple short codes for the same login/password combination, you will have to ask them where to put that short code in the BIND PDU. Note that this piece of information has to be put inside the BIND PDU, and not in SUBMIT_SM, because the BIND PDU is the only place that will allow routing MOs correctly.

See the [Information in each kind of PDU](#pdu) section above to know what fields are available in the BIND PDU, generally you would put the short code in *address_range*, but that requires special support from the provider. Contact them to know how they expect to route multiple short codes independently.

Adobe Campaign supports handling multiple short codes on the same external account just fine, so often just using a single account for all traffic will work fine.

#### An external account stopped working {#sms-external-account-not-working}

In general, SMPP connections tend to be very stable over time, and once they are configured correctly they should continue working.

* Investigate whether connector has been changed recently - and by whom (check External Accounts as a group).
* Investigate whether system was upgraded and when.
* Investigate whether any packages affecting SMS might have been upgraded recently.

If none of these checks lead to a root cause, contact the provider. Sometimes, when providers update their platforms, their connector behaves slightly differently. This might break fine tuned settings and introduce regressions.

It is recommended to keep in touch with the provider, they often communicate major changes in advance.

#### Issue with mid-sourcing (hosted)  {#sms-issue-hosted}

* If the problem happens on a mid-sourcing environment, make sure that the delivery and broadlogs are properly created and updated on the mid-sourcing server. If that is not the case, the issue is not an SMS issue.
* Make sure that the mid operator name is stricly in lower case otherwise the delivery will remain in pending status.
* If everything works on the mid server and SMS are properly sent, but the marketing instance is not properly updated, then you have a mid synchronization issue.

#### Issue when connecting to the provider {#sms-issue-connection}

* If the BIND PDU returns a non-zero *command_status* code (meaning there is an error), or if there is no BIND_RESP PDU, ask the provider why this happens.
* Check that the network is properly configured so the TCP connection can be made to the provider.
* Ask the provider to check that they properly allowed IP addresses of the Adobe Campaign instance (most providers require this).
* Check external account settings. Ask the provider in case of doubt about the value of some fields.
* If the connection is successful but unstable, check the [Issues with unstable connections](#unstable-connections). section below.
* If connection issues are difficult to diagnose, a network capture will bring you a lot of information. Make sure that the network capture runs simultaneously while the problem appears so it can be analyzed efficiently. You should also note the exact time at which the problem appears so it's easier to find the problem in network captures.

#### Issues with unstable connections {#unstable-connections}

**How to diagnose unstable connections:**

A connection is considered unstable if any of these things happen:

* The connection lasts for less than 1 hour.
* Restarting the SMS process will "fix" things temporarily. It probably means that an unstable connection triggers throttling, restarting the SMS process clears throttling, then it happens again until the root cause is found.
* The provider sends UNBIND PDUs. The provider should never send UNBIND PDUs in normal operation.
* *enquire_link* times out, either on the Campaign side or on the provider side. You may or may not see ENQUIRE_LINK_RESP with a non-zero error code in that case.
* There are a lot of BIND PDUs. There should not be more than a few during a day (it depends on the number of connections). More than 1 BIND PDU per hour and per connection should be alerting.

**How to fix connection stability problems:**

* Unstable connections are rarely the root cause, it's often the result of another problem triggering a disconnect in a way or another. Finding the root cause is the priority.
* Enable verbose SMPP traces. You will need them to see what's happening when the connection restarts.
* If the provider sends UNBIND PDUs, they probably do something wrong. Ask them why they send UNBIND and it will probably lead to the root cause.
* Taking a network capture is sometimes the only way to see how the connection is closed.
* If the provider closes the connections (by sending either a TCP FIN or a TCP RST packet), ask them why they do that. This should tell you the root cause of the problem.
* If the provider closes the connection after sending a clean error (such as DELIVER_SM_RESP with an error code), they must fix their connector because that prevents other kinds of messages from being transmitted and will trigger MTA throttling. This is especially important in transceiver mode where closing the connection impacts both MT and SR.
* If there are timeouts (BIND timeouts, SUBMIT_SM timeouts), Campaign may be sending messages too quickly for that provider. Try lowering the *max MT throughput* setting and see if it solves the issue.

#### Issue when sending a MT (regular SMS sent to an end-user)

* Check that the connection is stable: a SMPP connection should stay up for at least 1 hour continuously. See the section "Issue with unstable connections" above.
* If restarting the SMS process makes sending MT working again for a small period of time, you probably have throttling due to an unstable connection. See the section "Issue with unstable connections" above.
* Check that the broad log is present and in the correct status with the correct dates. If it's not, it's not a SMS issue but a delivery issue or a delivery preparation issue (that's outside the scope of this document).
* Check that the SMS connector is actually bound with the provider's equipment. Ask the provider for feedback to make sure all systems are communicating properly. See BIND_TRANSMITTER and BIND_TRANSCEIVER PDUs for information about the bind process. You may need to enable SMPP traces for proper troubleshooting.
* With the SMPP traces enabled, check that the SUBMIT_SM PDU is containing the right information (see the documentation above).
* Check that the provider responds with a SUBMIT_SM_RESP PDU with a "OK" value (code 0). Make sure that the PDU arrives with a reasonable delay: anything longer than 1 second is suspicious and must be discussed with the provider, it usually arrives in less than 100ms.
* If all these steps work, you can be confident that the problem is on the provider side. They will have to do troubleshooting on their platform.
* If it works but throughput is inconsistent, try adjusting the sending window and lowering the MT throughput. You will need to work with the provider to adjust that. Campaign can send messages very quickly so performance problems may arise on the provider's equipment.

#### MT are duplicated (the same SMS is sent multiple times in a row)

Duplicates are often caused by retries. It's normal to have duplicates when retrying messages, so you should concentrate your efforts on eliminating the root cause of retries.

* If you see duplicates sent exactly 60 seconds apart (or any other suspiciously "regular" period), it's probably a problem on the provider side, they don't send a SUBMIT_SM_RESP quick enough.
* If you see many BIND/UNBIND, you have an unstable connection: see the [Issues with unstable connections](#unstable-connections) section for solutions before attempting to solve duplicate messages issues.
* Check that all SUBMIT_SM PDUs have matching SUBMIT_SM_RESP shortly after. If they don't or SUBMIT_SM_RESP are too slow, the issue is on the provider side.

Mitigating the amount of duplicates when there is a retry:

* Lower the *sending window*. The sending window should be big enough to cover for SUBMIT_SM_RESP latency, but not too big. Its value represents the maximum number of messages that can be duplicated if an error happens while the window is full.

#### Issue when processing SR (delivery receipts)

* You will need SMPP traces enabled to do any kind of SR troubleshooting.
* Check that the DELIVER_SM PDU is coming from the provider and that it is well formed.
* Check that Campaign replies with a successful DELIVER_SM_RESP PDU in a timely manner. This guarantees that the SR has been inserted into the providerMsgStatus table for defered processing by the SMS process.

If the DELIVER_SM PDU is not successfully acknowledged, then you need to check a few things:

* Check regex related to id extraction and error processing in the external account. You may need to validate them against the content of the DELIVER_SM PDU.
* Check that errors are properly provisioned in the broadLogMsg table (the Campaign documentation explains this in details).

If the DELIVER_SM PDU has been acknowledged by the ACC extended SMPP connector but the broadLog is not updated properly, check the ID reconciliation process described in the section Matching MT, SR and broadlog entries above.

If you fixed everything but some invalid SR are still in the provider's buffers, you can skip them by using the "Invalid ID acknowledge count" option. This should be used with care and reset to 0 as quickly as possible after the buffers are clean.

If SR processing is slow, try qualifying the most common status messages in the BroadLogMsg table.

If only some SR are received but not all, check that no other system connect to your provider's account, such as a test system. SR can be routed on any connection, so some of them may be routed to this other system. The provider might help you finding where is this other system connecting to the account.

#### Issue when processing MO (and quarantine/auto reply)

* Enable SMPP traces during tests. If you don't enable TLS, it's always better to do a network capture when troubleshooting MO to check that PDUs contain the correct information and are properly formatted.
* When capturing network traffic or analyzing SMPP traces, be sure to capture the whole conversation with the MO and its reply MT (if a reply is configured).
* If the MO (DELIVER_SM PDU) doesn't appear in the traces, you can be confident that the problem is on the provider side. They will have to do troubleshooting on their platform.
* If the DELIVER_SM PDU appears, check that it's acknowledged by Campaign with a successful DELIVER_SM_RESP PDU (code 0). This RESP guarantees that all the processing logic has been applied by Campaign (auto reply and quarantine). If it's not the case, search for an error message in the SMS process logs.
* If automatic replies are enabled, check that the SUBMIT_SM has been sent to the provider. If not, it's guaranteed to find an error message in the SMS process logs.
* If the SUBMIT_SM MT PDU containing the reply is found in the traces but the SMS does not arrive to the mobile phone, you will have to contact the provider for assistance on troubleshooting because the problem is probably on their side.

#### Issue during delivery preparation not excluding quarantined recipients (quarantined by the auto reply feature)

* Check that the phone number format is exactly the same in the quarantine table and in the delivery log. If it's not, see the "Send full phone number" setting above if you are having issues with the plus prefix of the international phone number format.
* Check short codes: Exclusions happen if the short code of the recipient is either the same as defined in the external account or if it's empty (empty = any shortcode). If only one short code is used for the whole Campaign instance, it's easier to leave all "short code" fields empty.

#### Encoding issues  {#sms-encoding-issues}

Encoding issues are frequent in SMS. Here are a few basic steps.

**Step 1: Get in touch with the provider**

The provider is the expert that knows how SMS works. Contact them and see with them what's wrong. They should be able to tell you if the problem is on their side or in Campaign. If the problem is in Campaign, they should be able to tell you exactly what field is incorrect, which helps tremendously.

**Step 2: Know what's in your message**

You will have to know what's in your message. That sentence may sound easy, but it's not. Unicode allows so many variants for look-alike characters that Campaign cannot handle them all.

The most common source of problems is copy-paste from a word processor, that changes usual characters to typographically-correct versions: spaces changed to non-breaking spaces, double quotes changed to opening and closing quotes, minus signs changed to various kinds of hyphens ...

Don't copy-paste your message when testing, always type it directly in the interface.

**Don't be intimidated by hexadecimal**. Hexadecimal looks strange and unnatural, but it has a very distinct quality: you can tell the difference between similar characters. A lower-case L, a upper-case I, O, 0, all different types of quotes, non-latin encodings or even different types of spaces can all look the same (or even not being displayed at all). Hexadecimal shows everything and helps comparing things.

To convert unicode to hexadecimal, you can use online tools.

**When opening tickets** about encoding problems, whether with the provider or the Campaign support, **include a hexadecimal** version of what you type and what you see.

**Step 3: Know what you should send**

Determine the encoding you expect to be used and search online for its character table. Check that the characters you intend to send are actually available in the target code page. Check that the data_coding field is correct and matches what you and the provider expect.

**Step 4: Know what you actually sent**

You will need the debug output of the connector in order to see exactly what bytes you send to the provider. Encoding problems appear in SUBMIT_SM PDUs, so be sure to capture them. Send very distinct messages that are easy to find in the log.

Don't hesitate to send different kinds of special characters when testing. For example, GSM7 encoding has extended characters that are very distinct in their hexadecimal form, so they are easy to spot because they don't appear in any other encoding.

#### Performance issues {#sms-performance-issues}

>[!NOTE]
>
>Performance is a very broad topic. This section provides a few basic checks to do before attempting to scale or doing other big projects.

**Performance issues while sending MT**

* Check that all settings in the Throughput and delays section of the external account are correct, and that they match the settings allowed by the provider.
* Check that there are no retries.
* Check that the provider's infrastructure is not saturated. Check for RMSGQFUL or RTHROTTLED errors in RESP PDUs.
* Check serverConf settings. Start with default values and increase parameters slowly and one by one.
* Check that the SMS process doesn't restart all the time when under load. If it does, you may need to increase *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* and *maxProcessMemoryWarningMb* in the serverConf file.

**Performance issues while receiving SR**

If the provider complains about buffer overload on their side, this may be because Campaign doesn't receive SR fast enough.

* Check that the instance database is not overloaded. SR processing is very dependent on database performance.
* Ask the provider to increase the sending window for DELIVER_SM on their side. Ideally it should be as big as the *batchUpdateSize* setting in serverConf.

### Elements to include when communicating about a SMS issue

Whenever you seek assistance on a SMS issue (whether it's opening a support ticket to Adobe Campaign, to the SMS provider, or any kind of communication about the issue), you will need to include at least the following information to be sure that it will be properly qualified. Properly qualified issues are key to solving problems faster, so taking a little more time to try to understand the situation and give meaningful information will lead to a giant leap in efficiency.

* Enable verbose SMPP messages during the time when the problem appears. Most SMS problems are virtually impossible to solve without this.
* If the problem is related to SMS traffic, contact the provider first. They are the most knowledgeable and their platform is usually suited for efficient diagnosis of SMS traffic problems in real time.
* Include a brief but factual description of the problem.
* Include a description of the expected result.
* Include all the feedback from the provider.
* Include relevant logs and/or network captures. When doing captures, make sure to reproduce the problem during the capture or it will be useless.
* If you include logs, traces or captures, pinpoint the exact location in the file when the problem appears, as well as the exact location of a working example if there is any. Captures or traces can be big and tedious to look at, so anything helping to find information in them is helpful.
* If you reference messages, PDUs or logs, clearly state their timestamp so they are easy to find by other people.
* Try to reproduce the problem on a test environment. If you are unsure about a setting, try it on the test environment and check the result with the SMPP traces. It's usually better to report problems replicated on test environments than directly reporting problems on production environments.
* Include any change or tweaks made on the platform: even a small change can have huge impacts. Also, include any change that the provider may have done on their side.

#### When is a network capture useful?

A network capture is not always needed. Very often, verbose SMPP messages are enough. Here are some guidelines that will help you determine if a network capture is worth the effort:

* Connection issues, but the verbose messages don't show any BIND_RESP PDU.
* Unexplained disconnections with no error message (that's the behavior of the connector when it detects a low level protocol error).
* The provider complains about the unbind / disconnection process.
* There are encoding issues in optional TLV fields.
* Traffic is suspected to be mixed between different connections.

In all other situations, try to analyze verbose SMPP messages first and request a network capture only if it's clear that information is missing in the verbose logs.

#### When is a network capture useless?

In some cases, capturing network traffic is useless or just a waste of time. Here are the most common situations:

* TLS enabled: By definition, TLS traffic is encrypted so it cannot be captured.
* Performance issues: Logs contain all the needed information to trace performance issues.
* Timing issues (retry timing, enquire_link period, throughput capping, ...)
* SR parsing and processing: verbose logs give much more context and a better presentation.
* MO processing (automatic replies, quarantine).
* Errors not involving actual SMPP traffic: Delivery preparation, Message Center API issues, workflow issues, ...
