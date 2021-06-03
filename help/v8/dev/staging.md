---
product: Adobe Campaign
title: Campaign API staging mechanism
description: Campaign API staging mechanism
feature: Overview
role: Data Engineer
level: Beginner
---
# Campaign API staging mechanism

With Campaign Cloud database, blasting unitary calls is not recommended with regards to performances (latency & concurrency). Batching operation is always preferred. In order to improve performance, ingestion APIs are redirected to the local database.

Campaign staging capability is enabled by default on some built-in schemas. We can also enable it on any custom schema. Staging mechanism in a nutshell:

* Data schema structure is duplicated into the local staging table
* New APIs dedicated for data ingestion flow directly into the local staging table. [Learn more](new-apis.md)
* A scheduled workflow triggers every hour and synchronize data back to the Cloud Database. [Learn more](../config/replication.md).

Some built-in schemas are Staged by default, such as nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Campaign Classic v7 APIs are still available but cannot benefit from this new Staging mechanism: API calls flow to directly directly to the Cloud database. Adobe recommends to use new Staging mechanism as much as possible to reduce overall pressure and latency on Campaign Cloud database. 

>[!CAUTION]
>
>* With this new mechanism, data synchronization for channel optout, subscriptions, unsubscriptions or mobile registration is now **asynchronous**.
>
>* Staging only applies for schemas stored on Cloud Database. Do not enable staging on replicated schemas. Do not enable Staging on local schemas. Do not enable Staging on a Staged schema
>

## Implementation steps{#implement-staging}

To implement Campaign staging mechanism on a specific table, follow the steps below:

1. Create a sample custom schema on Campaign Cloud database. No staging enabled at this step.

    ```
    <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
            entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
            lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
            modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
    <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
            name="sampleTable">
        <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
        <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
    </element>
    </srcSchema>
    ```

    [!DNL :bulb:] Learn more about custom schema creation in [this page](create-schema.md).

1. Save and update the database structure.  [Learn more](update-database-structure.md)

1. Enable the staging mechanism in the schema definition by adding the **autoStg="true"** parameter.

    ```
    <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
            entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
            lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
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
