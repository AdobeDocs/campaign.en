---
solution: Campaign
product: Adobe Campaign
title: Campaign API staging mechanism
description: Campaign API staging mechanism
feature: Overview
role: Data Engineer
level: Beginner
---
# Campaign API staging mechanism

With Campaign Cloud database, blast unitary calls are not recommended due to performance (latency & concurrency). Batch operation is always preferred. In order to guarantee optimal performances of APIs, Campaign keeps handling API calls at the local database level.

Campaign staging mechanism is available for both built-in and custom table and brings the following advantages:

* Data schema structure is replicated in the local staging table
* [New APIs](new-apis.md) for ingestion flow directly into the staging table 
* A scheduled workflow triggers every hour and synchronize data back to the Cloud Database

Some built-in schemas are Staged by default, such as nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Campaign Classic v7 APIs are still available but cannot benefit from this new Staging mechanism: API calls flow to directly directly to the Cloud database. Adobe recommends to use new Staging mechanism as much as possible to reduce overall pressure and latency on Campaign Cloud database. 

>[!NOTE]
>With this new mechanism, data synchronization is now **asynchronous**.

## Implementation steps

To implement Campaign staging mechanism on a specific table, follow the steps below:

1. Create a sample custom schema on Campaign Cloud database. No staging enabled at this step.

    ```
    <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
            entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
            lastModified="YYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
            modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
    <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
            name="sampleTable">
        <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
        <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
    </element>
    </srcSchema>
    ```

    :bulb: Learn more about custom schema creation in [this page](create-schema.md).

1. Save and update the database structure.  [Learn more](update-database-structure.md)

1. Enable the staging mechanism in the schema definition by adding the **autoStg="true"** parameter.

    ```
    <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
            entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
            lastModified="YYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
            modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
    <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
            name="sampleTable">
        <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
        <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
    </element>
    </srcSchema>
    ```

1. Save the modification. A new staging schema is available, which is a local copy of the initial schema.

    ![](assets/staging-mechanism.png)

1. Update the database structure. The staging table will be created on Campaign local database.
