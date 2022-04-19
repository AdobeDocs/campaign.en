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

* [Learn about privacy and consent](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html){target="_blank"}.

* [Getting started with Privacy Management](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html){target="_blank"}.

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

Before creating Privacy requests, define the namespace you will use. The namespace is the key that will be used to identify the Data Subject in the Adobe Campaign database.

To learn more about identity namespaces, see the [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) documentation){target="_blank"}.

<!--ACC-->Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.

<!--However ACC doesn't support importing Identity Service Namespaces yet. So once you have created a new namespace on Identity namespace service, you need to create manually the namespace from ACC UI using the Administration > Platform > Namespaces menu, with the AEC namespace ID matching the one in Identity namespace.-->

1. Create a namespace on the [Identitiy Namespace service](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace).

    To learn more about identity namespaces, see the [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) documentation){target="_blank"}.

1. When [listing the identity namespaces available for your organization](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"}, you will get for example:

    ```
    {
            "updateTime": 1632903236731,
            "code": "accCPSTest",
            "status": "ACTIVE",
            "description": "test namespace",
            "id": 10998717,
            "createTime": 1632903236731,
            "idType": "Email",
            "namespaceType": "Custom",
            "name": "ACC CPS Test",
            "custom": true
    }
    ```

1. In Adobe Campaign, go to **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

    ![](assets/privacy-namespaces.png)

1. Select New.

    ![](assets/privacy-namespaces-new.png)

1. Fill in the new namespace details to match the namespace that you created on the Identitiy Namespace service:

    * the AEC Namespace ID must match the "id" attribute;
    * the Internal name must match the "code" attribute;
    * the Reconciliation key must match the "idType" attribute.

Please note that AEC namespace ID must match the one in Identity namespace.

Also, if creating requests on privacy UI/API then it may take some time for CPS to send namespaceID along with new custom namespace. ACC, ACS both process requests on basis of namespaceid so if its not present, request wont be handled. On stage I had observed this behavior, may not be applicable on prod.

Notes:

Request will NOT be processed if namespace doesnt exist on instance. Whoever is creating the request should ensure that namespace exists on instance also.
Standard namespaces email(6) and phone(7) are created by default
Any other namespaces which are to be used for privacy request processing must be created on the instance with proper details.
If a custom namespace has been created/ or a new standard namespace is being added to ACC
then with correct
AEC Namespace ID
Target mapping
Reconciliation key
namespace must be created on the instance

Corresponds to a custom namespace in the Organization this instance has been provisioned with. AEC Namespace ID must match id in Identity Namespaces.

Else request will not be processed and data will not be deleted/access data generated.

Create different requests for different namespaces. Every namespace should be requested in a different request for single reconciliation value. ACS and ACC both support single namespace per privacy request, so requests should be created with 1 namespace per request, if multiple namespaces are to be considered, create one request per namespace for same reconciliation value.
If creating requests via UI, only single namespace can be used, but consider this point when making request using CPS API.

<!--ACS - Also refer to this [tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) on how to create a namespace.-->

>[!NOTE]
>
>If you use several namespaces, create one Privacy request per namespace.

1. Click the Adobe Campaign logo in the top-left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

    ![](assets/xxx.png)

1. In the list of namespaces, click **[!UICONTROL Create]**.

    ![](assets/privacy-namespace-create.png)

1. Enter a **[!UICONTROL Label]**.

    ![](assets/privacy-namespace-label.png)

1. If you want to use an existing identity service namespace, choose **[!UICONTROL Map from Identity Namespace Service]** and select a namespace from the **[!UICONTROL Identity Service Namespaces]** list.

    ![](assets/privacy-map-from-namespace.png)

    If you want to create a new namespace in **[!UICONTROL Identity Service]** and map it in Campaign, select **[!UICONTROL Create new]** and enter a name in the **[!UICONTROL Identity namespace name]** field.

    ![](assets/privacy-create-new-namespace.png)

    To learn more about identity namespaces, see the [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) documentation.

1. One Identity Service Namespace is mapped to one namespace in Campaign. You must specify how the namespace will be reconciled in Campaign.

    Select a target mapping (**[!UICONTROL Recipients]**, **[!UICONTROL Real-time event]** or **[!UICONTROL Subscriptions to an application]**). If you want to use several target mappings, create one namespace per target mapping.

    ![](assets/privacy-namespace-target-mapping.png)

1. Choose the **[!UICONTROL Reconciliation key]**. This is the field that will be used to identify the Data Subject in the Adobe Campaign database.

    ![](assets/privacy-namespace-reconciliation-key.png)

1. Click **[!UICONTROL Create]**. You can now create Privacy requests based on your new namespace. If you use several namespaces, create one Privacy request per namespace.

### List of tables {#list-of-tables}

From ACC

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

>[!IMPORTANT]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.

### Privacy request statuses {#privacy-request-statuses}

Here are the different statuses for Privacy requests:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: in progress, the workflow has not processed the request yet.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: the workflow is processing the request.
* **[!UICONTROL Delete pending]**: the workflow has identified all the recipient data to delete.
* **[!UICONTROL Delete in progress]**: the workflow is processing the deletion.
* **[!UICONTROL Complete]**: the processing of the request has finished without an error.
* **[!UICONTROL Error]**: the workflow has encountered an error. The reason is displayed in the list of Privacy requests in the **[!UICONTROL Request status]** column. For example, **[!UICONTROL Error data not found]** means that no recipient data matching the Data Subject's **[!UICONTROL Reconciliation value]** has been found in the database.

## Opt-out for the Sale of Personal Information (CCPA) {#sale-of-personal-information-ccpa}

![](../assets/do-not-localize/book.png) The opt-out for the Sale of Personal Information, which is specific to CCPA, is explained in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests.html#sale-of-personal-information-ccpa){target="_blank"}.<!--move v7 section to a single page in ACC docs + update link-->