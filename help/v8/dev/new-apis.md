---
solution: Campaign
product: Adobe Campaign
title: New Campaign v8 APIs
description: New Campaign v8 APIs
feature: Overview
role: Data Engineer
level: Beginner
---
# New Campaign APIs{#gs-new-api}

You can use [all Campaign Classic v7 APIs](https://docs.adobe.com/content/help/en/campaign-classic/technicalresources/api/p-1.html) in Campaign v8. However, for subscriptions and unsubscription management, use the APIs [listed below](#sub-apis).

## Data management

Campaign v8 comes with three new APIs to manage data between Campaign local database and Cloud database. Prerequisites to use them is to enable the staging mechanism on the schema. [Learn more](staging.md).

* Ingestion API: xtk.session.ingest. This API is dedicated to Data Insert only.
* Data update/delete API: xtk.session.ingestExt
* xtk.session.lookup

A dedicated built-in workflow will synchronize the data in the Cloud Database.

## Data insert

The **xtk.session.ingest** API is dedicated to Data Insert only. No update/delete.

### Insert with no reconciliation

**In a workflow**

Use the following code in a **Javascript code** activity to insert data in the Cloud database without reconciliation.

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Once the workflow is executed, the staging table is fed as expected.

**From a SOAP call**

1. Get the authentication token. 
1. Trigger the API. The payload is:
    
    ```
    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
    <soapenv:Header/>
    <soapenv:Body>
        <urn:Ingest>
            <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
            <urn:domDoc>
                <sampleTableStg
                    testcol1="Test Value 1 (from SOAP)"
                    testcol2="Test Value 2 (from SOAP)"
                    xtkschema="dem:sampleTableStg">
                </sampleTableStg>
            </urn:domDoc>
        </urn:Ingest>
    </soapenv:Body>
    </soapenv:Envelope>
    ```

1. UUID is sent back to the SOAP response:

    ```
    <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
            <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
        </IngestResponse>
    </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    ```

As a result, staging table is fed as expected.

### Insert with reconciliation


## Data update/delete

The **xtk.session.IngestExt** API is optmized for data update/delete. For insert only, prefer **xtk.session.ingest**. Insert is working whether the record key is not in the staging table.


### Insert / update

**In a workflow**

**From a SOAP call**



## Subscription management {#sub-apis}

Subscription management in Campaign is decribed in [this page](../start/subscriptions.md).

Subscriptions and unsubscriptions can be managed with the following APIs:


>[!CAUTION]
>
>Subscriptions and unsubscriptions are **asynchronous** processes. Opt-in and opt-out requests are processed each hour through a specific technical workflow. [Learn more](../config/replication.md#tech-wf)

**Related topics**

* [Campaign Classic v7 JSAPI](https://docs.adobe.com/content/help/en/campaign-classic/technicalresources/api/p-1.html)
