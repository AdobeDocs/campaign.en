---
title: SMS connectors
description: Learn about SMS connectors in Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
exl-id: 5ec3f172-22dc-458b-8688-9974009c985e
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# About SMS connector types {#sms-connectors}

Adobe Campaign supports two SMS connectors used for sending SMS messages to your customers:

* **Legacy SMS connector**: First version of the connector used in Campaign v7 and earlier versions of Campaign v8. [Learn more](#legacy-sms-connector)
* **SMS connector v2**: Available in GA starting Campaign v8.9.1, this v2 dedicated SMS connector has been modernized to offer improved performance and reliability. [Learn more](#sms-connector-v2)

## Legacy SMS connector {#legacy-sms-connector}

The legacy SMS connector is the MTA-based SMS connector used in previous versions of Adobe Campaign. This connector is still supported for existing implementations, but Adobe strongly recommends upgrading to v8.9.1 or later to benefit from the improved performance and reliability of the v2 connector. 

To learn how to benefit from the v2 connector, refer to the [Activation](#activation) section.

For detailed information about the legacy SMS connector configuration and usage, refer to the [Campaign Classic documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## SMS connector v2 {#sms-connector-v2}

Available in GA starting v8.9.1, the v2 connector enables transceiver mode SMPP connections, persistent SMPP connections, and ensures better compatibility. A dedicated SMS external account is available for all SMS implementations using the v2 connector.

The v2 connector is enabled by default for new installations. If you upgraded from a previous version using the legacy connector, you need to contact your Adobe representative to switch to the v2 connector. See the [Activation](#activation) section.

To learn how to use the SMS connector v2 in Campaign v8, refer to the [SMS documentation](sms.md).

>[!NOTE]
>
>The v2 connector is also available in the following builds with some restrictions:
>* 8.8.1: release for all Campaign FDA environments. Not available for Campaign FFDA deployments.
>* 8.8.2: release for all deployment types including FFDA. Released in Limited Availability (LA).

## Activation {#activation}

### Why switch to the v2 connector {#why-switch-v2}

The dedicated SMS process introduces support for SMPP transceiver mode, reducing connection count and improving resource efficiency, while still supporting transmitter/receiver setups if needed. It offers significantly greater stability, with faster recovery from errors, persistent connections, and no reliance on local files or inter-process communication. Performance is also improved, with lower latency, higher throughput, and intelligent microbatching to balance speed and reliability. Additionally, the isolation of the SMS process simplifies troubleshooting and minimizes cross-channel impact. These enhancements make the dedicated connector a more robust and scalable solution for SMS delivery.

### Configuration {#configuration}

With Adobe Campaign Managed Cloud Services, the server configuration and SMS connector migration are managed by Adobe. This technical procedure requires direct access to the server configuration files and database operations.

To activate and start using the SMS connector v2, you first need to upgrade to v8.9.1 or later. Contact your Adobe representative or Adobe Customer Care. They will schedule and perform the necessary updates for your instance.
