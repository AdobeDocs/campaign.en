---
title: Manage Privacy requests in Campaign
description: Learn how to manage privacy requests in Campaign
feature: Privacy
role: Admin
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
---
# Manage Privacy requests in Campaign {#privacy}

Depending on the nature of your business and the jurisdictions it operates under, your data operations may be subject to legal privacy regulations. These regulations often give your customers the right to request access to the data you collect from them, and the right to request the deletion of that stored data. These customer requests for their personal data are referred to as "Privacy requests" throughout the documentation.

Adobe offers Data Controllers the tools to create and process Privacy requests for data stored in Campaign. However, it is your responsibility as a Data Controller to verify the identity of the Data Subject making the request, and to confirm that the data returned to the requester is about the Data Subject. Learn more on personal data and the different entities that manage data in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#personal-data){target="_blank"}.


To manage Privacy request in Campaign, you must first [define a namespace](#namespaces). You are then able to create and manage Privacy requests. To perform privacy requests, use the **Adobe Privacy Service** integration. Privacy requests pushed from the Privacy Service to all Adobe Experience Cloud solutions are automatically handled by Campaign via a dedicated workflow. [Learn more](#create-privacy-request)

![](../assets/do-not-localize/speech.png) Learn about the **Right to Access** and the **Right to be Forgotten** (delete request) in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#right-access-forgotten){target="_blank"}.

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Define a namespace {#namespaces}

Before creating a Privacy request, you must **define the namespace** to use. The namespace is the key which is used to identify the Data Subject in the database.

>[!NOTE]
>
>Learn more about identity namespaces in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html){target="_blank"}.

Currently Adobe Campaign does not support importing namespaces from the Experience Platform Identity Namespace service. Therefore, once you have created a namespace on the Identity Namespace service, you must create manually the corresponding namespace in the Adobe Campaign interface. To do this, follow the steps below.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Create a namespace on the [Identity Namespace service](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target="_blank"}.

1. When [listing the identity namespaces](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"} available for your organization, you get the namespace following details, for example:

    ```
    {
            "updateTime": 1632903236731,
            "code": "lumanamespace",
            "status": "ACTIVE",
            "description": "new namespace for Luma privacy requests",
            "id": 10998717,
            "createTime": 1632903236731,
            "idType": "Email",
            "namespaceType": "Custom",
            "name": "Luma Namespace",
            "custom": true
    }
    ```

1. In Adobe Campaign, browse to **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** and select **[!UICONTROL New]**.

    ![](assets/privacy-namespaces-new.png)

1. Enter a **[!UICONTROL Label]**.

1. Fill in the new namespace details to match the namespace that you created on the Identitiy Namespace service:

    * the **[!UICONTROL AEC Namespace ID]** must match the "id" attribute
    * the **[!UICONTROL Internal name]** must match the "code" attribute
    * the **[!UICONTROL Reconciliation key]** must match the "idType" attribute

    ![](assets/privacy-namespaces-details.png)

    The **[!UICONTROL Reconciliation key]** field will be used to identify the Data Subject in the Adobe Campaign database.

1. Select a target mapping <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> to specify how the namespace will be reconciled in Adobe Campaign.
    
    >[!NOTE]
    >
    >If you need to use several target mappings, create one namespace per target mapping.

1. Save your changes.

You can now create Privacy requests based on your new namespace. If you use several namespaces, create one Privacy request per namespace for the same reconciliation value.

## Create a Privacy request {#create-privacy-request}

The **[!DNL Adobe Experience Platform Privacy Service]** integration allows you to automate your Privacy requests in a multi-solution context through a single JSON API call. Adobe Campaign automatically handles the requests pushed from the Privacy Service through a dedicated workflow.

Refer to the [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} documentation to learn how to create Privacy requests from the Privacy Core Service.

Each **[!DNL Privacy Service]**  job is split into multiple Privacy requests in Adobe Campaign based on how many namespaces are being used, one request corresponding to one namespace.

Also, one job can be run on multiple instances. Therefore, multiple files are created for one job. For example, if a request has two namespaces and is running on three instances, then a total of six files are sent. One file per namespace and instance.

The pattern for a file name is : `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Campaign instance name
* **NamespaceId**: Identity Service Namespace ID of the namespace used
* **Reconciliation key**: Encoded reconciliation key

>[!CAUTION]
>
>To submit a request using the custom namespace type, leverage the [JSON method](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html#json){target="_blank"} and add the namespaceId to the request, or use the [API call](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html#access-delete){target="_blank"} to make the request.
>
>Only use the [Privacy user interface](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html#request-builder){target="_blank"} to submit requests using the standard namespace type.

### Tables searched when processing requests {#list-of-tables}

When performing a Delete or Access Privacy request, Adobe Campaign searches all the Data Subject's data based on the **[!UICONTROL Reconciliation value]** in all the tables that have a link to the recipient table (own type).

The list of built-in tables taken into account when performing Privacy requests are:

* Recipients (recipient)
* Recipient delivery log (broadLogRcp)
* Recipient tracking log (trackingLogRcp)
* Archived event delivery log (broadLogEventHisto)
* Recipient list content (rcpGrpRel)
* Visitor offer proposition (propositionVisitor)
* Visitors (visitor)
* Subscription history (subHisto)
* Subscriptions (subscription)
* Recipient offer proposition (propositionRcp)

If you created custom tables that have a link to the recipient table (own type), they will also be taken into account. For example, if you have a transaction table linked to the recipient table and a transaction details table linked to the transaction table, they will be both taken into account.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### Privacy request statuses {#privacy-request-statuses}

You can find below the different statuses for Privacy requests in Adobe Campaign and how to interpret them:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: in progress, the workflow has not processed the request yet.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: the workflow is processing the request.
* **[!UICONTROL Delete pending]**: the workflow has identified all the recipient data to delete.
* **[!UICONTROL Delete in progress]**: the workflow is processing the deletion.
* **[!UICONTROL Complete]**: the processing of the request has finished without an error.
* **[!UICONTROL Error]**: the workflow has encountered an error. The reason is displayed in the list of Privacy requests in the **[!UICONTROL Request status]** column. For example, **[!UICONTROL Error data not found]** means that no recipient data matching the Data Subject's **[!UICONTROL Reconciliation value]** has been found in the database.

**Related topics in Campaign Classic v7 documentation:**

* [Privacy and consent](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}

* [Getting started with Privacy Management](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html){target="_blank"}

* [Regulations on Privacy management](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#privacy-management-regulations){target="_blank"} (GDPR, CCPA, PDPA, and LGPD)

* [Opt-out for the Sale of Personal Information](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html){target="_blank"} (specific to CCPA)
