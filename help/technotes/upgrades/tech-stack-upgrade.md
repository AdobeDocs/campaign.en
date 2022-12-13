---
product: campaign
title: Technote - Adobe Campaign system upgrades
description: Adobe Campaign system upgrade
hide: yes
hidefromtoc: yes
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
---
# Adobe Campaign 2023 environment upgrades {#ac-system-upgrade}

Campaign infrastructure relies on third-party systems which must be regularly updated with the latest versions and fixes. These updates are mandatory to ensure continuity of service and secure Campaign environments from security risks. In addition, a Campaign upgrade is required to ensure compatibility with third-party system changes.

As a **Managed Cloud Services customer**, Adobe informs you about these upgrades when they are needed. Your environments will need to be upgraded in accordance with the recommendations to ensure compliance.

For security reasons, Adobe must [install the latest Campaign build](#ac-upgrade), and then upgrade your [operating system](#os-upgrade) and/or your [Relation Database Management System (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>For any questions about these changes, contact [Adobe Customer Care](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Campaign build upgrade {#ac-upgrade}

**Are you impacted?**

If you are impacted by the [operating system upgrade](#os-upgrade) and/or the [database system upgrade](#pg-upgrade) detailed below, Adobe must upgrade your Campaign environments to [the latest 8.4.3 version](../../v8/start/release-notes.md), which is compatible with these systems.

**How to update?**

As a Managed Cloud Services customer, Adobe will contact you and upgrade your Campaign version.

## Operating system upgrade {#os-upgrade}

**Are you impacted?**

If you are running Campaign on a Debian operating system, to benefit from latest Debian security updates, Adobe needs to move your Campaign infrastructure to **Debian 11**. Note that security support for Debian 9 will be available until June 30, 2023.

**How to update?**

As a Managed Cloud Services customer, Adobe will contact you and upgrade your environment.

## Database system upgrade {#pg-upgrade}

**Are you impacted?**

If your database system for Campaign is PostgreSQL, to benefit from latest PostgreSQL innovations and security updates, Adobe needs to upgrade to **PostgreSQL 14**. Note that PostgreSQL 11 will reach End Of Life on November 9, 2023.

**How to update?**

* As a Managed Cloud Services customer, Adobe will contact you and upgrade your database system from PostgreSQL 11 to PostgreSQL 14.
