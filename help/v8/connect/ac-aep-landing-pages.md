---
title: Work with Campaign and Adobe Experience Platform
description: Learn how to work with Campaign and Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
---
# Sync profile attributes using Adobe Campaign landing pages

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

## Setup an OAuth connection {#oauth}

Adobe Cloud Platform APIs use the OAuth 2.0 protocol for authentication and authorization. Using Adobe OAuth 2.0, you need to generate an access token using the OAuth Integration created in Adobe Developer Console, which is used to make API calls from your web server or browser-based app.

Detailed steps on how to obtain an OAuth 2.0 access token are available in the [developer console documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/OAuthIntegration/)

Once the OAuth-server-to-server connection is created, copy the following details from the adobe developer console. We will be using these values in ACC for authentication.

* CLIENT ID
* CLIENT SECRET
* ORGANIZATION ID

## Create an HTTP API Sources connection {#source}

The HTTP API source connector allows you to stream your data to Adobe Experience Platform, including any non-XDM-compliant data that you can map to an XDM-compliant dataset.

Detailed information on how to create an HTTP API source connection is available in [Adobe Experience Platform sources documentation]().

Once the Connection is created, copy the Inlet URL and sample schema payload from the connection.

## Add XTK options in Adobe Campaign {#xtk}

In order to be able to sync landing page data with Adobe Experience Platform, you need to add and configure specific XTP option in Adobe Campaigns, listed below:

* IMS_CLIENT_ID = cryptString(CLIENT ID)
* IMS_CLIENT_SECRET = cryptString(CLIENT SECRET)
* IMS_ORG_ID = ORGANIZATION ID
* IMS_CLIENT_API_KEY = cryptString(CLIENT ID)

>[!NOTE]
>
>Make sure you are using the cryptString() function to encrypt your data.



xtk option can be set from scripty activity with the logic to call this function once in Landing pages.


## Create a javascript code in Adobe Campaign {#javascript}

Add custom Javascript code into Adobe Campaign to allow data sync between landing pages and Adobe Experience Platform.

To do this, navigate to Administration→ Configuration→JavaScript codes under cus namespace then add the javascript code below. This set of code would be executing at server end.

* Add JS code for AEP profile update API calls

Copy below given snippet and paste to new java script code.

+++Javascript code

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

* If you want to fetch profile from AEP before loading web page, add below given method in above java script codes file. 

    Make sure to update body payload copied from platform UI.

    +++Javascript code

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

## Add the created javascript code into your landing pages {#script}

Once the javascript codes have been created into Adobe Campaign, you can leverage them into your landing pages using a **[!UICONTROL Script]** Activities Code that you need to add into your workfow. Make sure you modify the payload accordingly.

+++ Load profile from AEP

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

+++

+++ Update Adobe Experience Platfrom profile attributes

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

+++
