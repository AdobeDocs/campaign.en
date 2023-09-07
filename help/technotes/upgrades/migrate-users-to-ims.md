---
title: Migrate Campaign operators to Adobe Identity Management System (IMS)
description: Learn how to migrate Campaign operators to Adobe Identity Management System (IMS)
hide: yes
hidefromtoc: yes
---
# Migrate Campaign operators to Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Starting Campaign v8.6, the authentication process to Campaign v8 is being improved. All operators will use [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} only to connect to Campaign. Connecting with user/password will no longer be admitted. Adobe recommends to perform this migration in Campaign v8.5.2 to be able to migrate smoothly to Campaign v8.6.

This article details the steps required to migrate a technical operator to technical account on Adobe Developer console.

## What changed?{#move-to-ims-changes}

All Campaign regular users should already connect to the Adobe Campaign client console using their Adobe ID, through Adobe Identity Management System (IMS). However, with some older configurations, user/password connections were still available. This will no longer be permitted starting Campaign v8.6.

In addition, as part of the effort to reinforce security and authentication process, Adobe Campaign Client application now calls Campaign APIs directly using the IMS technical account token. Technical operators migration is detailled in a dedicated article, available in [this page](ims-migration.md).

This change is applicable starting Campaign v8.5.2, and will be **mandatory** starting Campaign v8.6. 


## Are you impacted?{#migrate-ims-impacts}

If operators in your organization are connecting to Campaign client console using their login/password (aka. native authentication), you are impacted, and must migrate these operator(s) to Adobe IMS as detailed below.

IMS migration is a security imperative to make your environments secure and standardized, as most of the other Adobe DX apps are already on IMS.

## How to migrate?{#ims-migration-procedure}

### Prerequisites{#ims-migration-prerequisites}

Before starting the migration process, you must reach out to your Adobe representative (Transition Manager) so that Adobe technical teams can migrate your existing Operator groups and Named rights to Adobe Identity Management System (IMS).

### Key steps {#ims-migration-steps}

Key steps for this migration are listed below: 

1. Adobe upgrades your environments to Campaign v8.5.2.
1. After the upgrade, you can still create new users with both methods, as native user or with IMS.
1. Your internal Campaign Administrator must add unique emails to all native users on the Campaign client console, and confirm to your Adobe Transition Manager once this is done. This step is detailed in [this section](#ims-migration-id).
1. Work with Adobe to secure a date for Adobe to run automated non technical user (operators) and product profiles migration. This step requires an hour window with no downtime to any of your instances.
1. Your internal Campaign Administrator validates these change and provide sign-off. After this migration, you must no longer create any further operator authenticating with his login and password.

You can now plan technical users migration to IMS according to [this technote](ims-migration.md), and confirm to your Adobe Transition Manager once done.
Adobe will then mark the migration as complete, and turn ON the flags to block new native user creation and native user login.

## Frequently Asked Questions? {#ims-migration-faq}

### When can you start the migration? {#ims-migration-start}

A prerequisite for the migration to Adobe Identity Management System (IMS) is to upgrade your environment to Campaign v8.5.2.

You can start IMS migration on your stage environment, once it is upgraded to Campaign v8.5.2, and accordingly plan for production environment.

### What happens after 8.5.2 build upgrade? {#ims-migration-after-upgrade}

After your environments have been upgraded to Campaign v8.5.2, you can perform Adobe Identity Management System (IMS) migration. 

New native user creation is still allowed until the IMS migration is complete. 

### When is the migration complete? {#ims-migration-end}

Once end-user migration and technical user migration to Adobe Identity Management System (IMS) is done, you must contact your Adobe Transition Manager so that Adobe can mark your migration as complete, and block user creation from the client console, and native user login.


### How to create users after migration? {#ims-migration-native}

Once full IMS migration is complete, Adobe will apply the restrictions which will block new native user creation. These restrictions are not applied until IMS migration is complete.

For new customers - new native user creation is not permitted from the beginning.

As a Campaign Administrator, you can grant permissions to the users of your organization through Adobe Admin Console and Campaign Client Console. Users log on to Adobe Campaign with their Adobe ID. Learn more in [this documentation](../../v8/start/gs-permissions.md).

### How to add emails for current native users? {#ims-migration-id}

As a Campaign Administrator, you must add email IDs to all native users from the client console. To perform this, follow the steps below:

1. Connect to the client console and browse to **Administration > Access Management > Operators**
1. Select the operator to update in the operator list.
1. Enter the email of the operator in the **Contact points** section of the operator form.
1. Save your changes.


### How to log in to Campaign via IMS? {#ims-migration-log}

Learn how to connect to Campaign with your Adobe ID in [this section](../../v8/start/connect.md).