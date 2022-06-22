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

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 



## Data loading (file) activity failed due to a backslash {#issue-2}

### Description{#issue-2-desc}

When injecting data into Snowflake cloud database with a Campaign load activity, the process can fail due to a backslash character is present in source file. The string is not escaped, and data is not processed correctly on Snowflake.

This issue only happens if the backslash is at the end of string, for example: "Barker\".


### Reproduction steps{#issue-2-repro}

1. Connect to the client console and create a workflow.
1. Add a **Data loading (file)** activity and configure it.
1. Select a local file with the characteristics described above.
1. Run the workflow and check the workflow logs to see the error.


### Error message{#issue-2-error}

````
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
````

### Workaround{#issue-2-workaround}

As a workaround, export the files with double quotes around the values like "Barker\" and include a file format option FIELD_OPTIONALLY_ENCLOSED_BY = '"'

### Internal reference{#issue-2-ref}

Reference: NEO-45549


## Data loading (file) activity failed to Upload file on server {#issue-3}

### Description{#issue-3-desc}

When uploading a file on Campaign server with a **Data loading (file)** activity, the process stops at 100% but never ends.

### Reproduction steps{#issue-3-repro}

1. Connect to the client console and create a workflow.
1. Add a **Data loading (file)** activity and configure it.
1. Select the **Upload on server** option.
1. Select the file on your local machine,
1. Click **Upload**


### Error message{#issue-3-error}

The process never ends.

### Workaround{#issue-3-workaround}

None

### Internal reference{#issue-3-ref}

Reference: NEO-47269