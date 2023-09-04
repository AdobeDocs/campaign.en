---
title: Work with Campaign and Adobe Experience Platform
description: Learn how to work with Campaign and Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
---
# Update Adobe Experience Platform profiles from Adobe Campaign landing pages

>[!IMPORTANT]
>
>Advanced users

Adobe Experience Platform **[!UICONTROL HTTP API]** Source connectors allows seamless integration between Adobe Campaign landing pages and Adobe Experience Platform. With this integration, you can:

* Fetch Adobe Experience Platform profile attributes to display updated information in Adobe Campaign landing pages,
* Send back updated profile attributes to Adobe Experience Platform to update the corresponding attributes based on what has been filled and submitted in the landing pages.

The main steps to setup this integration are as follows:

1. [Setup an OAuth connection](#oauth)
1. [Create an HTTP API Sources connection](#source)
1. [Add XTK options in Adobe Campaign](#xtk)
1. [Add javascript codes in Adobe Campaign](#javascript)
1. [Call javascript code into your landing pages](#script-activity)

## Setup an Oauth connection {#oauth}

Adobe Cloud Platform APIs use the OAuth 2.0 protocol for authentication and authorization. To connect Adobe Experience Platform to Adobe Campaign using API calls, you need to generate an access token using the OAuth Integration created in Adobe Developer Console.

To do this, access Adobe Developer Console and create a new Adobe API connection using the Adobe Experience Platform API product. Detailed steps on how to obtain an OAuth 2.0 access token are available in the [Adobe Developer Console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/Tools/OAuthPlayground/)

![](assets/ac-lp-oauth.png)

Once the OAuth-server-to-server connection has been created, access the **[!UICONTROL OAuth Server-to-Server]** menu and copy the details below, which are required in Campaign for authentication:

* CLIENT ID
* CLIENT SECRET
* ORGANIZATION ID

## Create an HTTP API Sources connection {#source}

The **[!UICONTROL HTTP API]** source connector allows you to stream your data to Adobe Experience Platform using APIs. 

The main steps to add an HTTP API source connector for Adobe Campaign are as follows. 

1. Navigate to Adobe Experience Platform **[!UICONTROL Sources]**, search for the **[!UICONTROL HTTP API]** source then click **[!UICONTROL Add data]**.

    ![](assets/ac-lp-source.png)

1. Configure the connection depending on your needs. Detailed information on how to configure an HTTP API connection is available in [Adobe Experience Platform sources documentation](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html).

    At **[!UICONTROL Authentication]** step, toggle on the **[!UICONTROL Enable authentication]** option to use the access token generated previously using OAuth integration.

    ![](assets/ac-lp-source-authentication.png)

1. Once the connection has been configured, the streaming endpoint displays, which is required to ingest data into Adobe Experience Platform. 

    ![](assets/ac-lp-endpoint.png)

    You can also access a sample of the format in which the data is ingested into Adobe Experience Platform. To do this, , open the newly created dataflow from the **[!UICONTROL Dataflows]** tab.

    ![](assets/ac-lp-schema.png)

## Add XTK options in Adobe Campaign {#xtk}

Once the connection of Adobe Campaign to Adobe Experience Platform has been configured, you need to add specific options into Adobe Campaign. This can be performed either from the Campaign console itself, or from a Script activity in your landing pages workflow.

+++Configure options from the console

Navigate to the **[!UICONTROL Administration]** / **[!UICONTROL Platform]** / **[!UIONTROL Options]**  menu and add the following options with the corresponding values from Adobe Developer Console:

* IMS_CLIENT_ID = cryptString(CLIENT ID)
* IMS_CLIENT_SECRET = cryptString(CLIENT SECRET)
* IMS_ORG_ID = ORGANIZATION ID
* IMS_CLIENT_API_KEY = cryptString(CLIENT ID)

>[!NOTE]
>
>Make sure you are using the cryptString() function to encrypt your data.

+++

+++Configure options at the landing pages workflow execution

To configure these options automatically at the execution of your landing pages workflow, add a **[!UICONTROL Script]** activity into your workflow with the code below:

    ```
    loadLibrary("xtk:shared/nl.js");
    loadLibrary("xtk:shared/xtk.js");
    loadLibrary("xtk:shared/json2.js");
    loadLibrary("xtk:common.js");

    function setAuthCredentials()
    {
    setOption("IMS_CLIENT_ID", cryptString('CLIENT ID'));
    setOption("IMS_CLIENT_SECRET", cryptString('CLIENT SECRET'));
    setOption("IMS_ORG_ID", cryptString('ORGANIZATION ID'));
    setOption("IMS_CLIENT_API_KEY", cryptString('CLIENT ID'));
    }
    ```

At workflow execution, the options are automatically created in the Campaign console with the provided values.

+++

## Create a javascript code in Adobe Campaign {#javascript}

To allow data sync between landing pages and Adobe Experience Platform, you need to asdd custom Javascript codes into Adobe Campaign which will be executed at server end.

To do this, follow navigate to the **[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL JavaScript codes]** menu and copy paste the below given snippet to a new java script code. 

>[!NOTE]
>
>Access token and authentication data are automatically retrieved from the options set up previously.

+++ Retrieve profile from Adobe Experience Platform before loading web page

This code checks if the profile exists in Adobe Experience Platform before loading the landing page. It fetches the profiles' data and display them in the landing page corresponding fields.

```
// API implementation to read profile from AEP
function getProfileInfo(email)
{
var accessToken = getAccessToken();
var request = new HttpClientRequest(('https://platform-stage.adobe.io/data/core/ups/access/entities?schema.name=_xdm.context.profile&entityId=' + email + '&entityIdNS=email&fields=identities,consents.marketing'));
request.method = 'GET';
request.header["Content-Type"] = "application/json";
request.header["sandbox-name"] = "prod";
request.header["x-gw-ims-org-id"] = getOption('IMS_ORG_ID');
request.header["x-api-key"] = getOption('IMS_CLIENT_API_KEY');
request.header["Authorization"] = "Bearer " + accessToken;
request.execute();
return request.response;
}
```

+++

+++ Adobe Experience Platform profile update

This code updates profile attributes in Adobe Experience Platform based on what is submitted using the landing page.

```
// API implementation to update profile in AEP
loadLibrary("xtk:shared/nl.js");
loadLibrary("xtk:shared/xtk.js");
loadLibrary("xtk:shared/json2.js");
loadLibrary("xtk:common.js");

function updateProfileInAEP(profileUpdatePayload)
{
var accessToken = getAccessToken();
var request = new HttpClientRequest('https://dcs-stg.adobedc.net/collection/64a300b84d61c0bcea4f0cd4ecaaa224a19477026d14f7e08b5408ffaf5e6162?syncValidation=false');
request.method = 'POST';
request.header["Content-Type"] = "application/json";
request.header["sandbox-name"] = "prod";
request.header["Authorization"] = "Bearer " + accessToken;
var body = '{"header":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"},"imsOrgId":"A1F66F0D5C47D1950A494133@AdobeOrg","datasetId":"63c7fa2a20cce11b98cccb41","source":{"name":"testHTTPSourcesVinay - 03/06/2023 5:43 PM"}},"body":{"xdmMeta":{"schemaRef":{"id":"https://ns.adobe.com/campdev/schemas/35d8e567772e1a1093ed6cf9e41d2c1fec22eeb3a89583e1","contentType":"application/vnd.adobe.xed-full+json;version=1.0"}},"xdmEntity":' + profileUpdatePayload +'}}';
request.body = body;
request.execute();
return request.response;
}


// Get Access token from OAuth-Server-to-server API call
function getAccessToken() {
var clientId = decryptString(getOption('IMS_CLIENT_ID'));
var clientSecret = decryptString(getOption('IMS_CLIENT_SECRET'));
var request = new HttpClientRequest(('https://ims-na1-stg1.adobelogin.com/ims/token/v2?grant_type=client_credentials' + '&client_id=' + clientId + '&client_secret=' + clientSecret + '&scope=openid,session,AdobeID,read_organizations,additional_info.projectedProductContext'));
request.method = 'POST';
request.execute();
var response = request.response;
if(response.code != 200){
  logError('GetAccessToken failed,', response.code, response.body);
  return;
}
var body = ''+response.body;
var parsedResponse = JSON.parse(body);
var accessToken = parsedResponse.access_token;
logInfo("Access token generated successfully");
return accessToken;
}
```

+++

## Add the created javascript code into your landing pages {#script}

Once the javascript codes have been created into Adobe Campaign, you can leverage them into your landing pages using a **[!UICONTROL Script]** activities that you need to add into your workfow.

Make sure you modify the payload accordingly depending on what you want to retrieve and modify.

if use the update script only, if profile doesn't exist in AEP, willl create the profile with the attributes. If do no ant to create the profile, use the load profile from AEP scrit: will check and ignore the update if doesn't exist.

+++ Load profile from AEP

```
// Script code to read profile from AEP.

logInfo("Loading profile from AEP");
loadLibrary("cus:aepAPI");
var recipient=ctx.recipient;
var email = recipient.@email;
var response = getProfileInfo(email);
ctx.isAEPProfileExists = 1;

if(response.code == 404){
  ctx.isAEPProfileExists = 0
  logInfo("Profile with email" + email + " not found in AEP, ignoring the update activity");
}
else if(response.code == 200){
  var body = ''+response.body;
  var parsedResponse = JSON.parse(body);
  for (var key in parsedResponse) {
    var value =  parsedResponse[key];
    var marketing = value.entity.consents.marketing;
    logInfo("User Consent Details : " + JSON.stringify(marketing));   
    if(marketing.hasOwnProperty('email')&&marketing.email.hasOwnProperty('val')&&marketing.email.val=='n'){
      ctx.recipient.@blackListEmail = 1;
    }
    if(marketing.hasOwnProperty('sms')&&marketing.sms.hasOwnProperty('val')&&marketing.sms.val=='n'){
      ctx.recipient.@blackListMobile = 1;
    }
    if(marketing.hasOwnProperty('push')&&marketing.push.hasOwnProperty('val')&&marketing.push.val=='n'){
      ctx.recipient.@blackListPostalMail = 1;
    }
  } 
}
```

+++

+++ Update Adobe Experience Platfrom profile attributes

```
// Script code to update profile in AEP and ACC.

logInfo("Executing script to update AEP profile.");

// Loading aepAPI library JS code
loadLibrary("cus:aepAPI");

var recipient=ctx.recipient

// Update profile only if it exists in AEP
if(ctx.isAEPProfileExists==1){
  
  var email = recipient.@email
  logInfo(email);
  logInfo(recipient.@blackListEmail);
  logInfo(recipient.@blackListMobile);
  logInfo(recipient.@blackListPostalMail);

  var optOutPayload = new Array();

  if(recipient.@blackListEmail==1){
    optOutPayload.push('"email":{"val":"n"}');
  }
  else
    optOutPayload.push('"email":{"val":"y"}');

  if(recipient.@blackListMobile==1){
    optOutPayload.push('"sms":{"val":"n"}');
  }
  else
    optOutPayload.push('"sms":{"val":"y"}');

  if(recipient.@blackListPostalMail==1){
    optOutPayload.push('"push":{"val":"n"}');
  }
  else
    optOutPayload.push('"push":{"val":"y"}');

  var profileUpdatePayload = '{'+ '"personalEmail":{"address":' + '\"' + email + '\"' + '},' +'"consents":{"marketing":{' + optOutPayload.toString() + '}}}';

  var response = updateProfileInAEP(profileUpdatePayload);
  if(response.code == 200){
  var body = '' + response.body;
  logInfo("AEP Profile Updated successfully, Response " + body);
  // Update ACC profile 
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
  }
  else{
    logError('Server Error: ', response.code, response.body);
  } 
}
else {
  logInfo("Ignoring AEP profile update as profile doesn't exists.");
  
  // Update ACC profile   
  recipient.@xtkschema = "nms:recipient";
  recipient.@_operation = "update";
  recipient.@_key="@id";  
  xtk.session.Write(recipient);
  logInfo("ACC Profile Updated successfully");
}
```

+++
