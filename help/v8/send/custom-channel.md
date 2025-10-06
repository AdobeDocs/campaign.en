---
title: Get started with custom channels
description: Learn how to create and send custom channel deliveries with Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
---
# Get started with custom channels {#gs-custom-channel} 

Adobe Campaign allows you to create custom external or API channels integrated with third-parties. You can then orchestrate and execute deliveries based on these channels. 

The delivery creation and sending can be performed both in the Client Console and in the Web UI. However, the custom channel configuration is only performed in the Client Console.

To learn how to create and send a delivery based on a custom channel, refer to this [page](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html){target="_blank"}.

Here are the steps to configure a new custom channel in the Client Console. These steps are common to custom external and API channels:

1. Configure the schema, [read more](#configure-schema)
1. Create a new external account, [read more](#create-ext-account)
1. Create a new delivery template, [read more](#create-template)

Custom API channels require additional configuration. [Read more](#api-additional)

## Configure the schema{#configure-schema}

First, you need to configure the schema to add the new channel to the list of available channels. 

1. From Campaign Explorer, select **Administration** > **Configuration** > **Data schemas**.

1. Create a schema extension to extend the **messageType** [enumeration](../config/enumerations.md) with the new channel.

    For example:

    ```
    <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
    <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
           value="122"/>
    </enumeration>
    ```

    ![](assets/cus-schema.png){zoomable="yes"}

## Create a new external account{#create-ext-account}

Then, you need to create a new routing external account.

1. From Campaign Explorer, select **Administration** > **Platform** > **External accounts**.

1. Create a new external account.

1. Select the channel and change the delivery mode. Choose **External** for custom external channels, and **Bulk** for custom API channels.

    ![](assets/cus-ext-account.png){zoomable="yes"}

## Create a new delivery template{#create-template}

Now, let's create the new template associated to the new channel.

1. From Campaign Explorer, select **Resources** > **Templates** > **Delivery templates**.

1. Create a new template.

1. Click on **Properties** and select the right folder and routing.

    ![](assets/cus-template.png){zoomable="yes"}

The new channel is now available. You can create and execute deliveries based on this channel.

## Custom API additional configuration{#api-additional}

Here are the main additional steps to configure custom API channels.

### Extend the schema{#api-additional-schema}

From the Client Console, extend the **Delivery** schema with all additional properties required for the custom channel. 

For more information on schema extension, refer to this [page](../dev/extend-schema.md).

### Set up the custom screen definition{#api-additional-screen}

From the Campaign Web UI, set up the custom screen definition:

1. Open the **Delivery** schema and click **Screen edition**. 

    ![](assets/cus-schema2.png){zoomable="yes"}

1. Select the tab that corresponds to your channel and define how the fields will be displayed in the content screen of the delivery. For more information on screen edition, refer to this [page](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/schemas.html#fields){target="_blank"}.

    ![](assets/cus-schema3.png){zoomable="yes"}

1. In the **Preview for simulate content** section, select the dedicated JSPP. This is optional. This will activate the preview in the delivery simulation screen. [Read more](#api-additional-preview)

### Configure the preview{#api-additional-preview}

This configuration is optional. If you want to activate the preview in the Web UI, in the delivery simulation screen, you need to configure a dedicated JSSP in the Client Console. 

When you click on **Open preview** in the delivery simulation screen in the Web UI, the following parameters are passed in the URL:

`https://adobe.campaign.adobe.com/cus/webPushMessagePreview.jssp?deliveryId=%40ToPzTurO9aGzQxYcMArBbA%3D%3D&id=%40oF8Fi17txuLmtiOFj4OIjQ%3D%3D`

* `deliveryId`: the delivery identifier
* `id`: the profile identifier

In the Client Console, select **Administration** > **Configuration** > **Dynamic JavaScript pages** and create a new JSSP. Here is an example with the parameters that need to be retrieved. 

```
<%@ page import="xtk:shared/nl.js"
%><%
  NL.require("/nl/core/shared/core.js")
    .require('/nl/core/jsspcontext.js')
    .require('/nl/core/shared/dataTypes.js')
    .require('/nl/core/schema.js');
    
  //response.setContentType("text/plain");
  var parameters = request.parameters;
  var deliveryId = decryptString(parameters.deliveryId);
  var oldUserContext = logonEscalation("neolane")
  
   var delivery = xtk.queryDef.create(<queryDef schema="nms:delivery" operation="getIfExists">
                                         <select>
                                           <node expr="[WebpushParameters/@richMediaOptions]" alias="@richMediaOptions"/>
                                           <node expr="[WebpushParameters/@mediaUrlInfo]" alias="@mediaUrlInfo"/>
                                           <node expr="[WebpushParameters/@WebpushMessageType]"/>
                                         </select>
                                         <where>
                                           <condition expr={"@id = " + NL.XTK.toXTKString(deliveryId)}/>
                                         </where>
                                       </queryDef>).ExecuteQuery();

  // Restore previous context
  logonWithContext(oldUserContext)
%>

<!DOCTYPE html ...
```

### Technical implementation{#api-additional-technical}

Depending on your custom channel, you will need to configure other parts of the application, such as: external accounts, target mapping, Javascript code for API, etc.

