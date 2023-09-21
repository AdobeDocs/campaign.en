---
title: Migrate Campaign sending infrastructure to Amazon Web Services (AWS)
description: Migrate Campaign sending infrastructure to Amazon Web Services (AWS)
hide: yes
hidefromtoc: yes
---

# Campaign sending infrastructure migration to Amazon Web Services (AWS) {#migrate-infra-to-aws}

## What changed?{#aws-changes}

As part of our ongoing effort to provide the highest quality email delivery service, the Campaign email sending infrastructure is being moved from Adobe hosted datacenters to Amazon Web Services (AWS). 

This move will ensure high availability, optimal throughput, and the ability to scale to meet our customers' needs.  

## Are you impacted?{#aws-impact}

This change affects:

* Campaign Classic v7 hosted and hybrid customers
* Campaign Managed Services customers
* All Campaign v8 customers
* Campaign Standard customers

## When will this migration happen?{#aws-timeline}

The development and staging environments migration will take place in **October 2023**. 

The production environments migration is scheduled to begin in **January 2024**. More details will be provided as the date approaches. 

As a Campaign customer, you will receive additional notification as the migration waves are scheduled. Notifications will be sent at least 7 days in advance of the migration for Stage environments, and at least 30 days in advance of the migration for Production environments.

## What is the impact?{#impact}

This move will be transparent to customers: 

* The length of each migration wave may vary depending on the number of impacted Campaign instances. When a migration wave is scheduled, the notification will include the expected duration.

* Campaign instances will be unable to send mail during the migration window. No other Campaign function will be affected.

 
## Frequently Asked Questions {#aws-faq}

* **Why is this a mandatory upgrade?**

    Adobe plans to decommission the legacy Data Center, Adobe Campaign instances running there must be transferred to the new reference Data Center, Amazon Web Services (AWS).

    The Adobe Managed Services cloud is hosted on Amazon Web Services (AWS), a modern, secure, and optimized environment. [Learn more about Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Which customers are targeted for this migration?**

    All the Campaign v8 customers and Campaign Classic v7 hybrid, hosted, and Campaign Managed Services will have their environments migrated. Campaign Standard customers are also impacted.

* **What is the expected downtime?**

    The migration is expected to take between 30min - 60min, but the length of each migration wave may vary depending on the number of impacted Campaign instances. When a migration wave is scheduled, the notification will include the expected duration.

* **Are there any actions required by the customer for migration?** 
    
    No actions is required since the migration will be ran automatically by Adobe. 

* **What validations need to be run by the customers?** 
    
    No specific testing is needed for this migration. In case any issue is observed, please reach out to [Adobe Customer Care](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Can I request a change in Date/Time to the scheduled security upgrade slot?** 
    
    Since this is a mandatory migration, we cannot accommodate modifications to the existing schedule.

For any other question, you can reach out to [Adobe Customer Care](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
