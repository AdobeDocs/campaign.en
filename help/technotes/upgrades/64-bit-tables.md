---
title: 64-bit schemas
description: Learn about 64-bit schemas in Adobe Campaign v8 for Campaign Standard migrated customers
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# 64-bit schemas {#sixty-four-bit-tables}

In order to facilitate the transition from Campaign Standard to Campaign v8, several tables have been changed from 32 to 64 bits. Indeed, Campaign Standard supports 64-bit PK in several out-of-the-box schemas, whereas Campaign v8 supports 32-bit PK in most schemas.

## Limitations

* This technical change only applies to customers migrating from Campaign Standard.
* Schema and broadlog extension is not supported in 64 bits. It will remain in 32 bits.
* Logs related to deliveries sent to technical users will not be available in Campaign v8.
* Only PostgreSQL is supported.

## Modified schemas

Here is the list of schemas changed to 64 bits and their modified attributes.

| Schema name | Attribute name |
|--- |--- |
| nms:broadLogRcp | id |
| nms:trackingLogRcp | id |
| nms:excludeLogRcp | id |
| nms:broadLogVisitor | id |
| nms:trackingLogVisitor | id |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | id |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | id |
| nms:trackingLogAppSubRcp | id |
| nms:excludeLogAppSubRcp | id |
| nms:webEvent | broadLogSrc-id, broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
