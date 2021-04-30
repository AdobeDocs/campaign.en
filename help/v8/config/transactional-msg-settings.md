---
solution: Campaign Classic
product: campaign
title: Campaign Transactional messaging settings
description: Campaign Transactional messaging settings
feature: Overview
role: Data Engineer
level: Beginner
---
# Transactional messaging settings

## Define permissions

To create new users for Message Center execution instances hosted on Adobe Cloud, you need to contact Adobe Customer Care. Message Center users are specific operators that require dedicated permissions to access ‘Real time events’ (nmsRtEvent) folders.

## Schema extensions 

All schema extensions made on the schemas used by **Message Center technical workflows** on either control or execution instances need to be duplicated on the other instances used by Adobe Campaign transactional messaging module.

:arrow_upper_right: Learn more about Message center technical workflows in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Send transactional push notifications

When combined with Mobile app channel module, transactional messaging enables you to push transactional messages through notifications on mobile devices.

:arrow_upper_right: The Mobile app channel is detailed in [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

To send transactional push notifications, you need to perform the following configurations:

1. Install the **Mobile App Channel** package onto the control and execution instances.

    >[!CAUTION]
    >
    >Check your licence agreement before installing a new Campaign built-in package.

1. Replicate the **Mobile application** service and the associated mobile applications on the execution instances.

In order for Campaign to send transactional push notifications, the event must contain the following elements:

* The mobile device ID: **registrationId** for Android and **deviceToken** for iOS. This ID represents the "address" that the notification will be sent to.
* The link to the mobile application or integration key (**uuid**) which lets you retrieve connection information specific to the application.
* The channel to which the notification will be sent (**wishedChannel**): 41 for iOS and 42 for Android.
* Other data to leverage for personalization.

Here is an example of an event that contains this information:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

