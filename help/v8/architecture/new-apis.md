---
title: New Campaign v8 APIs
description: New Campaign v8 APIs
feature: Architecture, API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: dd822f88-b27d-4944-879c-087f68e79825
---
# Specific FFDA Campaign APIs{#gs-new-api}

In the context of an [Enterprise (FFDA) deployment](enterprise-deployment.md), Campaign v8 comes with two specific APIs to manage data between Campaign local database and Cloud database. Prerequisites to use them is to enable the staging mechanism on the schema. [Learn more](staging.md)

* Ingestion API: **xtk.session.ingest**

    This API is dedicated to Data Insert only. [Learn more](#data-insert-api)
    
* Data update/delete API: **xtk.session.ingestExt**

    This API is used to update or delete data. [Learn more](#data-update-api)

A dedicated built-in workflow will synchronize the data in the Cloud Database.

## Insert data{#data-insert-api}

The **xtk.session.ingest** API is dedicated to Data Insert only. No update/delete.

### Insert with no reconciliation{#insert-no-reconciliation}

**In a workflow**

Use the following code in a **Javascript code** activity to insert data in the Cloud database without reconciliation:

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

![](assets/no-reconciliation.png)

### Insert with reconciliation

**In a workflow**

Use the following code in a **Javascript code** activity to insert data in the Cloud database with reconciliation:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Once the workflow is executed, the staging table is fed as expected.

![](assets/with-reconciliation.png)


**From a SOAP call**

1. Get the authentication token. 
1. Trigger the API. The payload is:
    
    ```
    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
    <soapenv:Header/>
    <soapenv:Body>
      <urn:Ingest>
         <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
         <urn:domDoc>
            <sampleTableStg  _key="@id" id="ABDCD321"
                 testcol1="Test Value 1 (from SOAP)"
                 testcol2="Test Value 2 (from SOAP)"
                 xtkschema="dem:sampleTableStg">
             </sampleTableStg>
         </urn:domDoc>
      </urn:Ingest>
     </soapenv:Body>
    </soapenv:Envelope>
    ```

1. In this case UUID is not provided back to the response because it has been provided in the payload. The response is:

    ```
    <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
            <pstrSUuids xsi:type="xsd:string"/>
        </IngestResponse>
    </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    ```

As a result, staging table is fed as expected.

## Update or delete data{#data-update-api}

The **xtk.session.IngestExt** API is optmized for data update/delete. For insert only, prefer **xtk.session.ingest**. Insert is working whether the record key is not in the staging table.

### Insert / update

**In a workflow**

Use the following code in a **Javascript code** activity to update data in the Cloud database:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Once the workflow is executed, the staging table is updated as expected.

![](assets/updated-data.png)

**From a SOAP call**

1. Get the authentication token. 
1. Trigger the API. The payload is:
    
    ```
    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
    <soapenv:Header/>
    <soapenv:Body>
        <urn:IngestExt>
            <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
            <urn:domDoc>
            <sampleTableStg  _key="@id" id="ABDCD321"
                    testcol1="Test Value E (from SOAP)"
                    testcol2="Test Value F (from SOAP)"
                    xtkschema="dem:sampleTableStg">
                </sampleTableStg>
            </urn:domDoc>
        </urn:IngestExt>
    </soapenv:Body>
    </soapenv:Envelope>
    ```

1. The SOAP response is:

    ```
    <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Body>
        <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
    </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    ```

As a result, staging table is updated as expected.

## Subscription management {#sub-apis}

Subscription management in Campaign is described in [this page](../start/subscriptions.md).

Insertion of subscription and unsubscription data relies on the [Staging mechanism](staging.md) in Campaign local database. Subscriber information is temporary stored in staging tables in the local database, and the synchronization workflow sends this data from the local database to the Cloud database. As a consequence, subscription and unsubscription processes are **asynchronous**. Opt-in and opt-out requests are processed each hour through a specific technical workflow. [Learn more](replication.md#tech-wf)


**Related topics**

* [Campaign JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
