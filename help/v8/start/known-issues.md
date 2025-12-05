---
title: Campaign v8 known issues
description: Known issues in the latest Campaign release
feature: Overview
role: Developer
level: Beginner
hide: yes
hidefromtoc: yes
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
---
# Known issues{#known-issues}

This page lists known issues identified in the **latest Campaign v8 Releases**. In addition, limitations coming with Campaign v8 are listed [in this page](ac-guardrails.md).


>[!NOTE]
>
>Adobe publishes this list of known issues at its own discretion. It is based on the number of customer reports, the severity, and the workaround availability. If an issue you are encountering is not listed, it may not have fit the criteria for publishing in this page.

## Campaign v8.3.8{#8.3-issues}

### Change Data Source activity issue {#issue-2}

#### Description{#issue-2-desc}

When injecting data into Snowflake cloud database with a Campaign **Query** and a **Change Data Source** activity, the process fails when a backslash character is present in the data. The source string is not escaped, and data is not processed correctly on Snowflake.

This issue only happens if the backslash character is at the end of string, for example: `Barker\`.


#### Reproduction steps{#issue-2-repro}

1. Connect to the Client Console and create a workflow.
1. Add a **Query** activity and configure it.
1. Select data with the characteristics described above.
1. Add a **Change Data Source** activity and configure it to select Snowflake cloud database.
1. Run the workflow and check the workflow logs to see the error.


#### Error message{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Workaround{#issue-2-workaround}

Workaround is to exclude data containing backslash character at the end of string, or remove it from the source file.


#### Internal reference{#issue-2-ref}

Reference: NEO-45549


### Data loading (file) activity failed to Upload file on server {#issue-3}

#### Description{#issue-3-desc}

When uploading a file on Campaign server with a **Data loading (file)** activity, the process stops at 100% but never ends.

#### Reproduction steps{#issue-3-repro}

1. Connect to the Client Console and create a workflow.
1. Add a **Data loading (file)** activity and configure it.
1. Select the **Upload on server** option.
1. Select the file on your local machine,
1. Click **Upload**


#### Error message{#issue-3-error}

The process never ends.

#### Workaround{#issue-3-workaround}

The workaround is to use an older Client Console. You will then be able to upload the file on the server.

As a Campaign administrator, you can download Campaign v8.3.1 Client Console in [Adobe Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&1_group.propertyvalues.operation=equals&1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&orderby.sort=desc&layout=list&p.offset=0&p.limit=4){target="_blank"}.

Learn how to access Adobe Software Distribution [in this page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html){target="_blank"}.

Learn how to upgrade your Client Console [in this page](connect.md)

#### Internal reference{#issue-3-ref}

Reference: NEO-47269

