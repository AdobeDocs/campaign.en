---
title: Campaign v8 known issues
description: Known issues in the latest Campaign release
feature: Overview
role: Data Engineer
level: Beginner
hide: yes
hidefromtoc: yes
---
# Known issues{#known-issues}

This page lists known issues identified in the **latest Campaign v8 Release**. In addition, limitations coming with Campaign v8 are listed [in this page](known-limitations.md).


>[!NOTE]
>
>Adobe publishes this list of known issues at its own discretion. It is based on the number of customer reports, the severity, and the workaround availability. If an issue you are encountering is not listed, it may not have fit the criteria for publishing in this page.

## Change Data Source activity issue {#issue-1}

### Description

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Workaround

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference

Reference: NEO-45549 


## Data loading (file) activity failed to Upload file on server {#issue-2}

### Description

File upload on Campaign server stops at 100% progress but never ends.

### Reproduction steps

1. Connect to the client console and create a workflow.
1. Add a **Data loading (file)** activity and configure it.
1. Select the **Upload on server** option.
1. Select the file on your local machine,
1. Click **Upload**

### Workaround

None

### Internal reference

Reference: NEO-47269