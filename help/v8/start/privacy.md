---
title: Privacy and consent in Campaign
description: Learn how to manage privacy and consent in Campaign
feature: Audiences
role: Data Engineer
level: Beginner

---
# Privacy and consent in Campaign {#privacy}

Adobe Campaign is a powerful tool for collecting and processing large volume of data, including personal information and sensitive data. It is therefore essential that you receive and monitor consent from your recipients.

Learn more in Campaign Classic v7 documentation:

* [Learn about privacy and consent](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}

* [Getting started with Privacy Management](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html){target="_blank"}

This information applies to GDPR, CCPA, PDPA, and LGPD. For more on these regulations, see [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#privacy-management-regulations){target="_blank"}.

![](../assets/do-not-localize/book.png) The opt-out for the Sale of Personal Information, which is specific to CCPA, is explained in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests.html#sale-of-personal-information-ccpa){target="_blank"}.<!--move v7 section to a single page in ACC docs + update link-->

## About Privacy requests {#about-privacy-requests}

In order to help you facilitate your Privacy readiness, Adobe Campaign allows you to handle Access and Delete requests.

To perform those requests, you must use the **Privacy Core Service** integration. Privacy requests pushed from the Privacy Core Service to all Experience Cloud solutions are automatically handled by Campaign via a dedicated workflow.

![](../assets/do-not-localize/book.png) Learn about the **Right to Access** and the **Right to be Forgotten** (delete request) in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html#right-access-forgotten){target="_blank"}.

## Prerequisites {#prerequesites}

Adobe Campaign offers Data Controllers tools to create and process Privacy requests for data stored in Adobe Campaign. However, it is the Data Controller's responsibility to handle the relationship with the Data Subject (email, customer care or a web portal).

It is therefore your responsibility as a Data Controller to confirm the identity of the Data Subject making the request and to confirm that the data returned to the requester is about the Data Subject.

>[!NOTE]
>
>For more on personal data and on the different entities that manage data (Data Controller, Data Processor and Data Subject), see [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html#personal-data){target="_blank"}.

## Namespaces {#namesspaces}

Before creating a Privacy request, you must define the namespace you will use. The namespace is the key that will be used to identify the Data Subject in the Adobe Campaign database.

>[!NOTE]
>
>To learn more about identity namespaces, see the [Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) {target="_blank"}.

Currently Adobe Campaign does not support importing namespaces from the Identity Namespace service. Once you have created a namespace on the Identity Namespace service, you must create manually the corresponding namespace from the Adobe Campaign interface. To do this, follow the steps below.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Create a namespace on the [Identity Namespace service](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target="_blank"}.

    <!--To learn more about identity namespaces, see the [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) documentation){target="_blank"}.-->

1. When [listing the identity namespaces](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"} available for your organization, you will get the namespace following details, for example:

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

1. In Adobe Campaign, go to **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** and select **[!UICONTROL New]**.

    ![](assets/privacy-namespaces-new.png)

1. Enter a **[!UICONTROL Label]**.

1. Fill in the new namespace details to match the namespace that you created on the Identitiy Namespace service:

    * the **[!UICONTROL AEC Namespace ID]** must match the "id" attribute;
    * the **[!UICONTROL Internal name]** must match the "code" attribute;
    * the **[!UICONTROL Reconciliation key]** must match the "idType" attribute.

    ![](assets/privacy-namespaces-details.png)

    The **[!UICONTROL Reconciliation key]** field will be used to identify the Data Subject in the Adobe Campaign database.

1. Select a target mapping (**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**) to specify how the namespace will be reconciled in Adobe Campaign.
    
    >[!NOTE]
    >
    >    If you want to use several target mappings, create one namespace per target mapping.

1. Save your changes.

You can now create Privacy requests based on your new namespace. If you use several namespaces, create one Privacy request per namespace for the same reconciliation value.

>[!CAUTION]
>
>Privacy requests will not be processed if the namespace was not created on your Adobe Campaign instance.

## Create a Privacy request {#create-privacy-request}

The Privacy Core Service Integration allows you to automate your Privacy requests in a multi-solution context through a single JSON API call. Privacy requests pushed from the Privacy Core Service to all Experience Cloud solutions are automatically handled by Campaign via a dedicated workflow.

Refer to the [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) documentation to learn how to create Privacy requests from the Privacy Core Service.

>[!CAUTION]
>
>To submit a request using the custom namespace type, leverage the [JSON method](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=en#json){target="_blank"} and add the namespaceId to the request, or use the [API call](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=en#access-delete){target="_blank"} to make the request.
>
>Only use the [Privacy user interface](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=en#request-builder){target="_blank"} to submit requests using the standard namespace type.

Each Privacy core service job is split into multiple Privacy requests in Campaign based on how many namespaces are being used, one request corresponding to one namespace. Also, one job can be run on multiple instances. Therefore, multiple files are created for one job. For example, if a request has two namespaces and is running on three instances, then a total of six files are sent. One file per namespace and instance.

The pattern for a file name is : `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Campaign instance name
* **NamespaceId**: Identity Service Namespace ID of the namespace used
* **Reconciliation key**: Encoded reconciliation key

## List of tables {#list-of-tables}

When performing a Delete or Access Privacy request, Adobe Campaign searches all the Data Subject's data based on the **[!UICONTROL Reconciliation value]** in all the tables that have a link to the recipient table (own type).

Here is the list of out-of-the-box tables that are taken into account when performing Privacy requests:

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

>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.

## Privacy request statuses {#privacy-request-statuses}

Here are the different statuses for Privacy requests:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: in progress, the workflow has not processed the request yet.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: the workflow is processing the request.
* **[!UICONTROL Delete pending]**: the workflow has identified all the recipient data to delete.
* **[!UICONTROL Delete in progress]**: the workflow is processing the deletion.
* **[!UICONTROL Complete]**: the processing of the request has finished without an error.
* **[!UICONTROL Error]**: the workflow has encountered an error. The reason is displayed in the list of Privacy requests in the **[!UICONTROL Request status]** column. For example, **[!UICONTROL Error data not found]** means that no recipient data matching the Data Subject's **[!UICONTROL Reconciliation value]** has been found in the database.
 