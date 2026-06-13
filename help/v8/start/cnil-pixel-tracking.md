---
title: Email Tracking Pixels and CNIL Guidance
description: Understanding CNIL's updated guidance on email tracking pixels and the Adobe Campaign capabilities that can support compliance efforts.
feature: Overview
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7, Campaign Standard
hide: true
---

# Understanding CNIL's updated guidance on email tracking pixels

This post is for informational purposes only. It is not legal advice and does not warrant your compliance with applicable law. The Adobe Campaign product capabilities described below are building blocks that, configured and operated appropriately, may support a compliant implementation. Each customer is responsible for determining and complying with its obligations under applicable law.

## Overview

On April 14, 2026, the _Commission nationale de l'informatique et des libertés_ (CNIL), France's data protection authority, published a [recommendation on the use of tracking pixels within emails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). The guidance clarifies when consent is required and highlights the importance of proper consent practices for email pixel tracking. This policy could impact sending practices for any entity delivering emails to subscribers based in France.

CNIL provided a three-month period from the date of the recommendation for companies to inform their email recipients ("users") of the presence of the tracking pixels, their purpose, and users' right to opt-out. During this transition period, customers are expected to notify users about pixel tracking and provide an opt-out if necessary. CNIL is expected to begin enforcement activities after July 14, 2026.

As the CNIL and other regulators clarify guidance on tracking pixels and related issues, Adobe will continue to monitor updates and inform customers of the technical capabilities of Adobe products that support email marketing, including Adobe Campaign.

Adobe email marketing execution applications, including Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign, and Marketo Engage, provide controls that can help customers manage open tracking at the delivery or email level. Customers are responsible for determining their own compliance obligations under applicable CNIL guidance and other laws, but these capabilities may support customer compliance efforts.

## What is an email tracking pixel

An email tracking pixel is a 1x1 transparent image embedded in the HTML of an email. When the recipient's email client loads that image, the pixel pings a server that records data such as a timestamp, device type, email client and sometimes an IP address for approximate location. That log is then tied to a recipient's record, allowing marketers to see whether an email is opened.

## Customer Support

Customers seeking assistance implementing the changes described above may engage with their existing Adobe ecosystem. For technical questions about the Adobe capabilities referenced, contact your Customer Success Manager or technical account manager.

## Adobe Campaign functionality related to email tracking

Customers may use Adobe Campaign's native tracking, schema, and personalization mechanisms to address certain elements when configuring architecture to address the CNIL guidance:

* **Classification of the delivery.** Extend `nms:delivery` with an `emailType` attribute (authentication, deliverability-only, transactional, marketing, public service, B2B prospecting). The classification drives which pixels are allowed without consent.

* **Consent capture.** Extend `nms:recipient` with a per-purpose consent structure carrying wording version, timestamp, capture source, and expiry. Extend sign-up forms and preference centers to collect pixel consent separately from the email opt-in.

* **Pixel emission.** Define one `NmsTracking_OpenFormula` per pixel purpose (authentication, deliverability, performance, profiling, fraud detection). A delivery typology rule selects which formulas to emit based on emailType and the recipient's per-purpose consent. Personalization blocks encapsulate the logic so it does not live in individual creatives.

* **Withdrawal.** Add a **Manage tracker preferences** link to every email footer, distinct from the unsubscribe link. The link points to an `nms:webApp` landing page authenticated through `idTracking`; the recipient withdraws consent in one click, without re-entering their email address. A filter step added to the standard **Tracking** workflow prevents re-opens of previously delivered emails from being exploited after withdrawal.

* **Proof of consent.** Capture each consent event in an append-only log (a `pix:consentLog` extension namespace, for example), with the wording version stored separately for retrievability after wording changes. Surface the log through the Adobe Campaign explorer and as a periodic export.
* **Re-solicitation governance.** A `lastPixelRefusalDate` field and a filtering typology rule prevent re-solicitation for at least six months after a refusal. A periodic workflow can help manage consent expiration.

* **Reporting.** Existing Adobe Campaign reporting continues to operate against the new fields (urlCategory, emailType, the consent flags) without code changes.

For more information regarding email tracking in Adobe email marketing execution applications see documentation here:

| Product | Documentation reference |
|---|---|
| Campaign v8 | [Message Tracking](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [Get started with message tracking](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [Configuring email channel](https://experienceleague.adobe.com/en/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [Message tracking documentation](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [Disable tracking for an email link](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [Email settings documentation](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


