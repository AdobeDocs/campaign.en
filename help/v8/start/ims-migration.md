---
title: Migration of tech users to Technical account on Developer console
description: Migration of tech users to Technical account on Developer console
hide: yes
hidefromtoc: yes
---
# Migration of Campaign technical operators to Adobe Developer Console {#migrate-tech-users-to-ims}

Starting Campaign v8.5, the authentication process to Campaign v8 is being improved. Technical operators must use [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} to connect to Campaign. A technical operator is a Campaign user profile which has been explicitly created for API integration. This article details the steps required to migrate a technical operator to technical account on Adobe Developer console.

## What changed?{#ims-changes}

Campaign regular users already connect to the Adobe Campaign console using their Adobe ID, through Adobe Identity Management System (IMS). As part of the effort to reinforce security and authentication process, Adobe Campaign Client application now calls Campaign APIs directly using the IMS technical account token. 

Learn more about the new server to server authentication process in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

This change is applicable starting Campaign v8.5, and will be **mandatory** starting Campaign v8.6. 


## Are you impacted?{#ims-impacts}

If you are using Campaign APIs, you need to migrate your technical operator(s) to Adobe Developer Console as detailed below.

## How to migrate?{#ims-migration-procedure}

### Prerequisites{#ims-migration-prerequisites}

Before starting the migration process, you must reach out to your Adobe representative so that Adobe technical teams can migrate your existing Operator groups and Named rights to Adobe Identity Management System (IMS).

### Step 1 - Create/update your Campaign project in Adobe Developer Console{#ims-migration-step-1}

Integrations are created as part of a **Project** within Adobe Developer Console. Learn more about Projects in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}. 

As a Campaign v8 user, you should already have a project in the Adobe Developer Console. If not, you must create a project. Steps to create a project are detailed [in Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Once you have access to your Campaign project, you can add services including APIs, Adobe Campaign, and I/O Management API. For this migration, you must add below APIs in your project: **I/O Management API** and **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Step 2 - Add an API to your project using Server to Server authentication{#ims-migration-step-2}

Once your project is created in the Adobe Developer Console, add an API that uses Server-to-Server authentication. Learn how to set up the OAuth Server-to-Server credential in [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

When the API has been successfully connected, you can access the newly generated credentials including Client ID and Client Secret, as well as generate an access token.

### Step 3 - Add the product profile to the project{#ims-migration-step-3}

You can now add your Campaign product profile to the project, as detailed below:

1. Open the Adobe Campaign API.
1. Click the **Edit product profiles** button

    ![](assets/do-not-localize/ims-edit-api.png)

1. Assign all the relevant Product Profiles to the API, for example 'messagecenter', and save your changes.
1. Browse to the **Credential details** tab of your project, and copy the **Technical Account Email** value.

### Step 4 - Update the technical operator in the Client Console {#ims-migration-step-4}


This step is only required if specific folder permissions or named rights have been defined for this operator (not via the operator's group).

You now need to update the newly created technical operator in Adobe Campaign Client Console. You must apply the existing technical operator folder permissions to the new technical operator.
To update this operator, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Access the existing technical operator used for APIs.
1. Browse to the folder permissions, and check rights.
1. Apply the same permissions to the newly created technical operator. This operator's email is the **Technical Account Email** value copied earlier.
1. Save your changes.


<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### Step 5 -Validate your configuration {#ims-migration-step-5}

To try out the connection, follow the steps detailed in the [Adobe Developer Console credentials guide](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} for generating an access token and copy the Sample cURL command provided.


### Step 6 - Update the third-party API integrations {#ims-migration-step-6}

You must update the API integrations with your third-party systems. 

For further more details about API integration steps, including a sample code for smooth integration, refer to [Adobe Developer Console authentication documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Soap calls samples{#ims-migration-samples}

Once the migration process is achieved and validated, the Soap Calls are updated as below:

* Before the migration

    ```sql
    POST /nl/jsp/soaprouter.jsp HTTP/1.1
    Host: localhost:8080
    Content-Type: application/soap+xml;
    SOAPAction: "nms:rtEvent#PushEvent"
    charset=utf-8
    
    <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
    <soapenv:Header/>
    <soapenv:Body>
        <urn:PushEvent>
            <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
            <urn:domEvent>
                <!--You may enter ANY elements at this point-->
                <rtEvent type="type" email="name@domain.com"/>
            </urn:domEvent>
        </urn:PushEvent>
    </soapenv:Body>
    </soapenv:Envelope>
    ```

* After the migration

    ```sql
    POST /nl/jsp/soaprouter.jsp HTTP/1.1
    Host: localhost:8080
    Content-Type: application/soap+xml;
    SOAPAction: "nms:rtEvent#PushEvent"
    charset=utf-8
    Authorization: Bearer <IMS_Technical_Token_Token>
    
    <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
    <soapenv:Header/>
    <soapenv:Body>
        <urn:PushEvent>
            <urn:sessiontoken></urn:sessiontoken>
            <urn:domEvent>
                <!--You may enter ANY elements at this point-->
                <rtEvent type="type" email="name@domain.com"/>
            </urn:domEvent>
        </urn:PushEvent>
    </soapenv:Body>
    </soapenv:Envelope>
    ```
