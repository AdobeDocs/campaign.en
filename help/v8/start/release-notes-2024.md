---
title: Campaign v8 (console) 2023 release notes
description: List of features and improvemens coming with 2023 Campaign v8 releases
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
---
# 2024 release notes {#2024-rn}

This page lists new capabilities, improvements, and fixes coming with **2024 Campaign v8 Releases**.


## Release 8.6.2 {#release-8-6-2}

_Feb 23, 2024_

### Fixes {#fixes-8-6-2}

This release fixes the following issue:

* Fixed a performance issue that could occur on the mid-sourcing instance (NEO-72595).

## Release 8.6.1 {#release-8-6-1}

_Feb 14, 2024_

### New features {#new-8-6-1}

* Starting this release, you have access to the new **Campaign Web user interface**, available through the central Adobe Experience Cloud environment. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. From its intuitive interface, you can quickly access your cloud applications, product features, and services. Learn how to connect to Adobe Experience Cloud, and access Adobe Campaign Web interface [in this page](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 now integrates with **Adobe Experience Manager as a Cloud Service**, with authoring exclusively available via the Adobe Campaign Web User Interface. [Learn more](../connect/ac-aem.md)

* You can now use your **Adobe Experience Manager Assets library** alongside your Experience Cloud Assets even if the Integration with the Adobe Experience Cloud package is installed on your Adobe Campaign instance. [Learn more](../connect/ac-aem.md#assets-library)

### General improvements {#improvements-8-6-1}

* Campaign v8.6 brings improved throughput for **email deliveries tracking indicators**. With our optimized processes, tracking ingestion and compute time is reduced, and you can check your delivery key indicators much faster.


### Deliverability updates {#deliverability-8-6-1}

* By February 2024, any company sending more than 5,000 email messages through Google or Yahoo! will have to start using an authentication technology known as Domain-based Message Authentication Reporting and Conformance (DMARC). Make sure to have DMARC record set up for all the subdomains that you are using with Adobe Campaign. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html){target="_blank"}

* Starting June 1st, 2024, Google and Yahoo! will be requiring senders to comply with One-Click List-Unsubscribe. Adobe Campaign now supports this option. [Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Fixes {#fixes-8-6-1}

The following issues are fixed in this release:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789
