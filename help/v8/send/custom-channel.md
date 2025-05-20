---
title: Get started with custom external channels
description: Learn how to create and send custom external channel deliveries with Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
---
# Get started with custom external channels {#gs-custom-channel} 

Adobe Campaign allows you to create custom external channels integrated with third-parties. You can then orchestrate and execute deliveries based these channels. 

The delivery creation and sending can be performed both in the Client Console and in the Web UI. However, the custom external channel is only performed in the Client Console.

To learn how to create and send a delivery based on a custom external channel, refer to this [page](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Here are the steps to create a new external custom channel in the Client Console:

1. Configure the schema, [read more](#configure-schema)
1. Create a new external account, [read more](#create-ext-account)
1. Create a new delivery template, [read more](#create-template)

## Configure the schema{#configure-schema}

First, you need to configure the schema to add the new channel to the list of available channels. 

1. From Campaign Explorer, select **Administration** > **Configuration** > **Data schemas**.

1. Create a schema extension to extend the messageType enumeration with the new channel.

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

1. Select the channel and change the delivery mode to **External**.

    ![](assets/cus-ext-account.png){zoomable="yes"}

## Create a new delivery template{#create-template}

Now, let's create the new template associated to the new channel.

1. From Campaign Explorer, select **Resources** > **Templates** > **Delivery templates**.

1. Create a new template.

1. Click on **Properties** and select the right folder and routing.

    ![](assets/cus-template.png){zoomable="yes"}

The new channel is now available. You can create and execute deliveries based on this channel.
