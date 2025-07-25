---
title: Setting-up API access
description: Learn how to set up access to Campaign Standard APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
---
# Setting up API access {#setting-up-api-access}

Adobe Campaign Standard API access is set up through the steps below. Each of these steps is detailed in the [Adobe Developer documentation](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>To manage certificates in [Adobe Developer](https://developer.adobe.com/), make sure you have **System administrator** rights on the organization or a [developer account](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Admin Console.

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.
1. **Create a new integration to Adobe Campaign Service** in [Adobe Developer](https://developer.adobe.com/) and configure it. Your credentials will then be generated (API Key, Client secret...).
1. **Create an OAuth Server-to-Server** credential by following these [implementation steps](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

    >[!IMPORTANT]
    >
    >JWT (JSON Web Tokens) is currently in the process of depreciation and is being replaced with OAuth. The transition is being carried out progressively within Campaign's upcoming releases. The Service Account (JWT) credentials have been marked as deprecated, they will continue to work until Jan 27, 2025. Therefore you must migrate your application or integration to use the new OAuth Server-to-Server credential before Jan 27, 2025. OAuth authentication is preferred. You will find all the elements to migrate from JWT authentication to OAuth authentication on these pages:
    >* [Migration](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
    >* [Implementation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
    >* [Deprecation JWT FAQ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

To establish a secure service-to-service Adobe I/O API session, every request to an Adobe service must include in the Authorization header the information below.

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'

```

* **&lt;ORGANIZATION&gt;**: This is your personal ORGANIZATION ID, one ORGANIZATION ID is provided by Adobe for each of your instances :

    * &lt;ORGANIZATION&gt; : your production instance,
    * &lt;ORGANIZATION-mkt-stage&gt;: your stage instance.

    To obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer documentation</a>).

* **<ACCESS_TOKEN>**: Your personal access token, that was retrieved when exchanging your JSON Web Token through a POST request.

* **<API_KEY>**: your personal API Key. It is provided in Adobe I/O after creating a new integration to Adobe Campaign Service.

    ![alt text](assets/tenant.png)
    
## Troubleshooting

During AdobeIO integration, if the following error appears:

```

{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}

```


Refer to your administrator or your Adobe technical contact to check if the CNAME parameter is created correctly.
