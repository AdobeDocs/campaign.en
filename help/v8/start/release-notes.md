---
title: Campaign v8 release notes
description: Latest Campaign v8 release
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
---
# Latest releases {#latest-release}

This page lists new capabilities, improvements and fixes coming with Campaign v8 (console) latest releases. Learn more about Campaign releases, versions, and upgrades in [this page](upgrades.md).

## Release 8.6.4 {#release-8-6-4}

_Jan 15, 2025_


### General improvements {#improvements-8-6-4}

* Campaign v8.6.4 allows native authentication mode, restricted to existing users already connecting to Campaign with a native name/password authentication. As a reminder, to ensure a higher security level, Adobe strongly recommends you to move to Adobe Identity Management System (IMS) and connect to Campaign using your Adobe ID. IMS is also a prerequisites the access to Campaign Web User Interface. Note that if you are using your Adobe ID to connect to Campaign, you must not move back to the native authentication mode. Learn how to move to Adobe IMS in [this technote](../../technotes/upgrades/migrate-users-to-ims.md).
* Campaign application stability has been improved during delivery analysis in the context of an [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md).

### Security improvements {#security-8-6-4}

* Connection with Adobe solutions and apps through the **[!UICONTROL Adobe Experience Cloud]** external account has been updated to reinforce security. 

### Compatibility updates {#comp-8-6-4}

* Databricks is now supported as an external database with Adobe Campaign Federated Data Access (FDA). Learn more [in this page](compatibility-matrix.md#FederatedDataAccessFDA).

### Fixes {#fixes-8-6-4}

The following issues are fixed in this release:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81520, NEO-81566, NEO-81704, NEO-83096, NEO-83081.