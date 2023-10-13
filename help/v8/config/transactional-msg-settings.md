---
title: Campaign Transactional messaging settings
description: Campaign Transactional messaging settings
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
---
# Transactional messaging settings {#mc-settings}

Transactional messaging (Message Center) is a Campaign module designed for managing triggered messages. Learn more about Transactional messaging in [this section](../send/transactional.md).

Understand transactional messaging architecture in [this page](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to install and configure Campaign Transactional messaging in your environment.

## Define permissions {#mc-permissions}

To create new users for Message Center execution instances hosted on Adobe Cloud, you need to contact Adobe Customer Care. Message Center users are specific operators that require dedicated permissions to access 'Real time events' (nmsRtEvent) folders.

## Schema extensions  {#mc-schema-ext}

All schema extensions made on the schemas used by [Message Center technical workflows](#technical-workflows) on either control or execution instances need to be duplicated on the other instances used by Adobe Campaign transactional messaging module.

## Send transactional push notifications {#mc-transactional-push}

When combined with [Mobile app channel module](../send/push.md), transactional messaging enables you to push transactional messages through notifications on mobile devices.

To send transactional push notifications, you need to perform the following configurations:

1. Install the **Mobile App Channel** package onto the control and execution instances.

    >[!CAUTION]
    >
    >Check your license agreement before installing a new Campaign built-in package.

1. Replicate the **Mobile application** service and the associated mobile applications on the execution instances.

In addition, the event must contain the following elements:

* The mobile device ID: **registrationId** for Android and **deviceToken** for iOS. This ID represents the "address" that the notification is sent to.
* The link to the mobile application or integration key (**uuid**) which lets you retrieve connection information specific to the application.
* The channel to which the notification will be sent (**wishedChannel**): 41 for iOS and 42 for Android.
* Any other personalization data.

Below is an example of an event configuration to send transactional push notifications:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

## Purge events {#purge-events}

You can adapt the deployment wizard settings to configure how long the data is to be stored in the database.

Event purging is carried out automatically by the **Database cleanup** technical workflow. This workflow purges the events received and stored on the execution instances and events archived on a control instance.

Use the arrows as appropriate to change the purge settings for the **Events** (on an execution instance) and **Archived events** (on a control instance).


## Technical workflows {#technical-workflows}

You must ensure that the technical workflows on your control and execution instances have been started before deploying any transactional message templates.

These workflows can then be accessed from the **Administration > Production > Message Center** folder. 

### Control instance workflows {#control-instance-workflows}

On the control instance, you must create one archiving workflow for each **[!UICONTROL Message Center execution instance]** external account. Click the **[!UICONTROL Create the archiving workflow]** button to create and start the workflow.

### Execution instance workflows {#execution-instance-workflows}

On the execution instance(s), you must start the following technical workflows:

* **[!UICONTROL Processing batch events]** (internal name: **[!UICONTROL batchEventsProcessing]** ): this workflow lets you break down batch events in a queue before they are linked to a message template.
* **[!UICONTROL Processing real time events]** (internal name: **[!UICONTROL rtEventsProcessing]** ): this workflow lets you break down real time events in a queue before they are linked to a message template.
* **[!UICONTROL Update event status]** (internal name: **[!UICONTROL updateEventStatus]** ): this workflow lets you attribute a status to the event.

  Possible event statuses are:

    * **[!UICONTROL Pending]**: the event is in the queue. No message template has been assigned to it yet.
    * **[!UICONTROL Pending delivery]**: the event is in the queue, a message template has been assigned to it and it is being processed by the delivery.
    * **[!UICONTROL Sent]**: this status is copied from the delivery logs. It means that the delivery has been sent.
    * **[!UICONTROL Ignored by the delivery]**: this status is copied from the delivery logs. It means that the delivery was ignored.
    * **[!UICONTROL Delivery failed]**: this status is copied from the delivery logs. It means that the delivery failed.
    * **[!UICONTROL Event not taken into account]**: the event could not be linked to a message template. The event will not be processed.
