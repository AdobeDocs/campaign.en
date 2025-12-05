---
title: Moving to the new SMS connector v2
description: Learn how to move to the new SMS connector v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
---
# Moving to the new SMS connector v2

Adobe Campaign v8 introduces a new **dedicated SMS process connector** (v2), which offers improved performance and reliability compared to the legacy MTA-based SMS connector.

## Why Switch to the v2 connector

The dedicated SMS process introduces support for SMPP transceiver mode, reducing connection count and improving resource efficiency, while still supporting transmitter/receiver setups if needed. It offers significantly greater stability, with faster recovery from errors, persistent connections, and no reliance on local files or inter-process communication. Performance is also improved, with lower latency, higher throughput, and intelligent microbatching to balance speed and reliability. Additionally, the isolation of the SMS process simplifies troubleshooting and minimizes cross-channel impact. These enhancements make the dedicated connector a more robust and scalable solution for SMS delivery.

## Configuration

With Adobe Campaign Managed Cloud Services, the server configuration and SMS connector migration are managed by Adobe. This technical procedure requires direct access to the server configuration files and database operations.

If you need to migrate to the new SMS connector v2, contact your Adobe representative or Adobe Customer Care. They will schedule and perform the necessary updates for your instance.

For more information about the SMS channel in Campaign v8, refer to the [SMS documentation](../../v8/send/sms/sms.md).
