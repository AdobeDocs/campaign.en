---
title: SMPP connector in delivery properties
description: About the settings of SMPP connector in deliveries
feature: SMS
role: User
level: Beginner, Intermediate
---

# SMPP connector description {#smpp-connector-desc}

>[!IMPORTANT]
>
>This applies to Adobe Campaign v8.7.2 and later.
>
>For older versions, refer to the [Campaign Classic v7 documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

## SMS connector data flow

This section describes how the SMS process handles data.

Here is a high level block diagram that summarizes how the SMS process interacts with its environment.

![](assets/smsv2_highlevel.png){zoomable="yes"}

The SMS process hosts 2 important components: the SMPP connector itself that handles communication with the SMPP provider, and a background task for SR reconciliation.

### Data flow for SMPP accounts

The SMS process polls nms:extAccount and spawns new connections in its SMPP connector, passing settings of each account. Polling frequency can be adjusted in serverConf, in the *configRefreshMillis* setting.

For each active SMPP account, the SMPP connector tries to keep connections active all the time. It reconnects if the connection is lost.

### Data flow while sending messages

* The SMS process selects active deliveries by scanning nms:delivery. A delivery is active if:
    * Its state implies that messages can be sent
    * Its validity period is not expired
    * It is actually a delivery (e.g. it is not a template, it is not deleted)
    * The SMPP connector could open at least one connection for the external account linked to the delivery
* For each delivery, the SMS process loads delivery parts. If the delivery part was partially sent, the SMS process checks which messages were already sent by checking the broad log.
* The SMS process expands the template with personalization data from the delivery part.
* The SMPP connector generates a MT (SUBMIT_SM PDU) matching the content and other settings.
* The SMPP connector sends the MT through a transmitter (or transceiver) connection.
* The provider returns an ID for this MT. It is inserted into nms:providerMsgId.
* The SMS process updates the broad log to the sent status.
* In case of final error, the SMS process updates the broad log accordingly, and may create a new kind of error in nms:broadLogMsg.

### Data flow while receiving SR

* The SMPP connector receives and decodes the SR (DELIVER_SM PDU). It uses regexes defined in the external account to get message id and status.
* Message id and status are inserted into nms:providerMsgStatus
* After being inserted, the SMPP connector replies with a DELIVER_SM_RESP PDU.
* If anything went wrong during the process, the SMPP connector sends a negative DELIVER_SM_RESP PDU and logs a message.

### Data flow while receiving a MO

* The SMPP connector receives and decodes the MO (DELIVER_SM PDU).
* The keyword is extracted from the message. If it matches any declared keyword, corresponding actions are executed. It may write to nms:address to update quarantine.
* If custom TLV are declared, they are decoded according to their respective settings.
* The fully decoded and processed MO is inserted into the nms:inSms table.
* The SMPP connector replies with a DELIVER_SM_RESP PDU. If any error was detected, an error code will be returned to the provider.

### Data flow while reconciling MT and SR

* The SR reconciliation component periodically reads nms:providerMsgId and nms:providerMsgStatus. Data from both tables is joined.
* For all messages that have an entry in both tables, the matching nms:broadLog entry is updated.
* The nms:broadLogMsg table may be updated in the process if a new kind of error is detected, or to update counters for errors that were not manually qualified.

## Matching MT, SR and broadlog entries

Here is a diagram describing the whole process:

![](assets/message_processing.png){zoomable="yes"}

**Phase 1**

* The message is scanned, formatted then transmitted to the SMPP connector.
* The SMPP connector formats it as a SUBMIT_SM MT PDU.
* The MT is sent to the SMPP provider.
* The provider replies with SUBMIT_SM_RESP. SUBMIT_SM and SUBMIT_SM_RESP are matched by their sequence_number.
* SUBMIT_SM_RESP provides an id coming from the provider. This id is inserted along with the broad log id into the nms:providerMsgId table.

**Phase 2**

* The provider sends a DELIVER_SM SR PDU.
* The SR is parsed to extract provider id, status and error code. This step uses extraction regexes.
* The provider id and its corresponding status are inserted into nms:providerMsgStatus.
* When all data is safely inserted into the database, the SMPP connector replies with DELIVER_SM_RESP. DELIVER_SM and DELIVER_SM_RESP are matched by their sequence_number.

**Phase 3**

* The SR reconciliation component of the SMS process scans both nms:providerMsgId and nms:providerMsgStatus tables periodically.
* If any row has matching provider ids in both tables, the 2 entries are joined together. This allows matching the broad log id (stored in providerMsgId) with the status (stored in providerMsgStatus)
* The broad log is updated with the corresponding status.

## Affinities and the dedicated process connector

Affinities are ignored by the dedicated process connector, it just runs inside the SMS process.

## serverConf options {#serverconf-options}

Some settings can be tuned in serverConf.xml. Like any other settings in this file, it should be specified in the config-instance.xml file. All settings are in the < mta2 > element.

This table summarizes all settings. Min/max sensible values give a rough idea of the range you should consider in most cases. Debugging value is the value to choose when trying to find issues that are not related to performance.

| Setting | Description | Default | Minimum sensible value | Maximum sensible value | Debugging value |
|:-:|:-:|:-:|:-:|:-:|:-:|
| batchUpdateSize | Size of update microbatches | 5000 |100: Very low latency | maxWaitingMessages/updateThreads: Going above this value is useless because maxWaitingMessages will limit buffering anyway | 1: Disable microbatching, update messages one by one |
| configRefreshMillis | Period for configuration reloading in milliseconds | 10000 | pollPeriodMillis: Low latency | 600000: Don't reload too fast to save resources | 500: Low latency allows trying new settings faster |
| deliveryPartRetryCount | Maximum number of times a deliveryPart is retried or postponed. Caution: restarting the sending process counts as a retry, crashes may count as a retry too. | 20 | 1: Disable retries | 50: Make messages more persistent to work around unstable providers | 1: Disable retries. 1000: Avoid flushing failed messages. |
| deliveryPartRetryDelaySeconds | Minimum delay before retrying a deliveryPart. This is cross process and cross container. Delay is in seconds. | 60 | 0: Immediate retries | 3600: Very slow retries (1 hour between each retry) | 1: Makes retries easy to follow in busy logs. |
| logOutput | Send monitoring & profiling data on main log output. | true | false: May increase throughput a bit. Discouraged. | true: Enable logging. | true |
| maxWaitingMessages | Maximum number of messages processed at any time | 50000 | 256: Enough for a single deliveryPart | 200000: Limited by SQL query length (64k) | 1: Process messages one by one |
| pollPeriodMillis | Database polling frequency (in milliseconds) to check for new messages | 2000 | 500: Very low latency | 10000: Bigger batches | 500: Low latency makes debug easy. |
| prepareThreads | Number of threads for message preparation | 3 | 1: Single threaded | Number of CPUs. Be careful with RAM usage. Increasing above 6 may require increasing maxSMSMemoryMb, maxProcessMemoryAlertMb and maxProcessMemoryWarningMb | 1: Single threaded generates cleaner logs. |
| profDeliveryStat | Log various aggregated statistics about internals of the SMS process | true | false: May increase throughput a bit. Discouraged. | true: Low verbosity log | true |
| profLogPerMessage | Log each processing step for each message | false | false: Reduce log verbosity. | true: Very high verbosity log. **Use only when absolutely necessary**. Big performance impact. **Please disable this setting as soon as enough data has been gathered**. | true |
| providerIdScanPeriod | Period in seconds between scans for new provider ids to reconcile | 10 | 1: Low latency | 60: Bigger batches for more throughput | 1: Low latency helps debugging message processing. |
| providerIdThreads | Number of threads for provider id reconciling. 1 thread per instance is enough. Set to 0 to disable on this container. | 1 | 0: Disable on this container | 1 | 1 |
| sendingThreads | Number of sending threads | 1 | 1: Single threaded | Number of CPUs. Too many threads usually hurt performance. | 1: Single threaded generates cleaner logs. |
| updateThreads | Number of threads for updating database | 1 | 1: Single threaded | Number of CPUs. Each thread creates its own DB connection. | 1: Single threaded generates cleaner logs. |
| verifyMode | Simulate sending messages. Messages are not actually sent. Useful for debugging | false | false | true |false: Run the system normally. true: Test DB access and message preparation only.|
