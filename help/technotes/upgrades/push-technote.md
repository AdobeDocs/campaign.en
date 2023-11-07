---
product: campaign
title: Push Notification Channel upcoming changes
description: Push Notification Channel upcoming changes
hide: yes
hidefromtoc: yes
---
# Push Notification Channel upcoming changes {#push-upgrade}

This page describes the upcoming Changes to Push Notification Channel via Firebase Cloud Messaging in Adobe Campaign Classic.

Where are important changes to the Firebase Cloud Messaging (FCM) service that may impact your Adobe Campaign Classic implementation.

As part of Google's continual effort to improve its services, the legacy FCM APIs will be discontinued in June 2024 (Firebase Cloud Messaging HTTP protocol: https://firebase.google.com/docs/cloud-messaging/http-server-ref)

These APIs are currently integrated with Adobe Campaign Classic to send Push Notification Messages. We understand that many of our customers, like you, rely on these services for your marketing campaigns and communication needs and especially for Android devices.

## How Does This Impact You?

* **HTTP (Legacy) API Users**: If any of your active push notification campaigns utilize the HTTP (legacy) API, your setup will be directly impacted by this change. We strongly encourage you to review your current configurations and prepare for the migration to the newer APIs.

* **Good News for HTTP v1 API Users**: If your setup exclusively uses the HTTP v1 API for Android Push notifications, then you are already in compliance and no further action will be required on your part.

## What Are We Doing?

* **Transition Plan**: Our team is actively working on developing a comprehensive transition plan. This will ensure that, when needed, you can update your implementation to the newer FCM APIs already available in recent versions of Adobe Campaign and with minimal disruption to your campaigns.

* **Detailed Instructions**: We will provide a step-by-step guide and other resources to facilitate a smooth transition process.

* **Support**: Our Customer Support Team will be available to assist you throughout this transition. We may also host webinars and enablement sessions to cover the technical aspects and best practices for the transition.

## How Does This Impact You?

* **Stay Informed**: Keep an eye on your inbox for further communications from us, including the detailed transition plan.

* **Review Current Setup**: Take this time to review your current configuration and customization in Adobe Campaign Classic so you are prepared to make any necessary changes if required.

* **Contact Us**: If you have any immediate concerns or questions, please don't hesitate to reach out to our support team.

## Implementation steps 

In the coming weeks, we will be sharing more details about the transition plan for Legacy FCM APIs, including timelines and action items. Rest assured, our primary goal is to make this transition as seamless as possible for you and your team.

We appreciate your business and thank you for your understanding as we adapt to these changes. Your success is our top priority, and we're committed to supporting you every step of the way.

So you can anticipate the change, here are the general steps that will be needed to migrate your push configuration from HTTP (Legacy) to FCM HTTPv1 API.

### Build upgrade

* Campaign Classic: the support of HTTPv1 has been added in AC7 20.3.1 release. If you're using a previous version, you must first upgrade to the latest Campaign Classic build.

* Campaign v8: HTTPv1 is supported by all Campaign v8 releases. No upgrade needed.

### Marketing server

Configuration changes can be performed by the customer/partner.

1. First, you need to extract your JSON file. The Firebase Admin SDK service's account JSON file is needed to have the mobile application moved to HTTPv1. Refer to this [page](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Navigate to your list of **Services and Subscriptions**.

1. Locate all mobile applications using the HTTP (legacy) API version.

1. For each of these mobile applications, set the **API version** to HTTPv1 and follow the configuration instructions detailed in the [documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>The switch to HTTPv1 API will be taken into account for new deliveries. Deliveries in retry, in progress, and in use will still use the HTTP (legacy) API.

### Mid Sourcing Server

There are no changes required.

### Real-time execution server

You need to contact Adobe Campaign support for this. The migration procedure is the same as for the marketing server. 

### Android OS and Android Mobile Application

There are no specific changes required to the Android Mobile applications' code and the notification behavior should not change.

Nevertheless, HTTPv1 is introducing three new payload elements:

| Name  | Default value   |
|---|---|
| sticky | False |
| priority | Default |
| visibility | False |
| sticky | Private |
