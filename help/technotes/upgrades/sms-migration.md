---
title: Moving to the new SMS connector v2
description: Learn how to move to the new SMS connector v2
feature: Technote
role: Admin
hide: yes
hidefromtoc: yes
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
---
# Moving to the new SMS connector v2

This document outlines the procedure and key considerations when migrating from the MTA-based SMS connector to the new **dedicated SMS process connector** in Adobe Campaign v8.

## Why Switch to the v2 connector

The dedicated SMS process introduces support for SMPP transceiver mode, reducing connection count and improving resource efficiency, while still supporting transmitter/receiver setups if needed. It offers significantly greater stability, with faster recovery from errors, persistent connections, and no reliance on local files or inter-process communication. Performance is also improved, with lower latency, higher throughput, and intelligent microbatching to balance speed and reliability. Additionally, the isolation of the SMS process simplifies troubleshooting and minimizes cross-channel impact. These enhancements make the dedicated connector a more robust and scalable solution for SMS delivery.

## Differences v1 and v2 connectors

The dedicated SMS connector in Adobe Campaign v8 introduces several architectural changes compared to the MTA-based connector. One key difference is the default use of SMPP transceiver mode, which reduces the number of connections by combining send and receive functions. If the provider doesn’t support this mode, it's still possible to use separate transmitter and receiver connections. Unlike the MTA connector, enabling automatic replies has no effect on connection count, and all receiver connections can handle any type of incoming message.

Connection count is now calculated using a different formula: 

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

The sendingThreads parameter, defined in the serverConf, defaults to 1 and should generally remain unchanged unless specifically optimizing for high performance. Because a single process handles all SMS traffic, managing parallelism through these parameters becomes critical to control system load and behavior.

The sending window behaves similarly to the MTA connector but has an even greater impact on performance in the dedicated mode. Larger sending windows reduce database IOPS and improve throughput. Campaign can efficiently handle windows of over 1000 messages, provided that the provider supports this and the use case allows for a small margin of message loss or duplication in case of connection issues. On the provider side, configuring a larger SR sending window can also significantly improve delivery report throughput.

Finally, while MO (Mobile Originated) message handling remains functionally unchanged, the underlying code has been updated. Throughput per connection is still limited the same way, but the dedicated connector enables much faster burst sending. However, without throughput limits, high-speed sending may overwhelm provider or system resources, making it advisable to set explicit MT throughput caps in the external account configuration.

## Switching Procedure

To ensure a smooth switch to the dedicated SMS process, it's best to perform the operation during low or no SMS traffic. Some buffered messages may be lost or left in an invalid state if MTA buffers aren't fully flushed. It's also normal to miss some SRs for up to a week after the switch, due to unpredictable SR timing. Not following these precautions can lead to message loss or duplication, despite built-in safeguards.

Both SMS connectors use different formats for SR (Status Report) processing. Although both rely on the `NmsProviderMsgId` table, they interact with it differently. Therefore, switching connectors requires clearing the entire table to prevent conflicts or orphaned data. There are several ways to perform this cleanup. Below are the SQL queries you can use:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Steps

1. Review `serverConf` settings (`sms > mta2`).
1. Pause real-time message preparation workflow (if applicable).
1. Pause all SMS deliveries.
1. Disable the SMS external account.
1. Stop and restart the MTA and SMS processes.
1. Ensure no SMPP connections are active. If present, ensure all deliveries are paused.
1. Clear the contents of the `NmsProviderMsgId` and `NmsProviderMsgStatus` tables in the database.
1. In the external account:
    * Enable the "Dedicated process" checkbox
    * Adjust other settings: MTA child connections, MT throughput, Sending window
1. Re-enable the external account and save.
1. Resume SMS deliveries.
1. Check that SMS services work normally.

>[!NOTE]
>
>Monitor SMS, MTA, and MTA child logs for errors or issues.
>
>Save previous external account settings for rollback purposes.

### Rollback Procedure

Rolling back to the MTA connector is possible by following the same steps used during the initial switch, in the same order. This includes stopping or pausing all SMS deliveries and restoring the original external account configuration.

1. If the instance uses real-time deliveries, pause the technical workflow responsible for preparing those messages.
1. Pause all SMS deliveries.
1. Disable the SMS external account.
1. Stop and restart both the MTA and SMS processes.
1. Ensure that no SMPP connections remain active; if they do, verify that all deliveries are properly paused.
1. Clear the `NmsProviderMsgId` and `NmsProviderMsgStatus` tables in the database.
1. In the external account:
    * Uncheck the "dedicated process" option in the external account.
    * Restore all previous external account settings: MTA child connections, MT throughput, Sending window
1. Re-enable and save the external account.
1. Resume all SMS deliveries.
1. Finally, confirm that SMS services are functioning normally.
