---
solution: Campaign v8
product: Adobe Campaign
title: Campaign external accounts
description: Campaign external accounts
feature: Overview
role: Data Engineer
level: Beginner
---

# Configure your external accounts

Adobe Campaign comes with a set of pre-defined external accounts. In order to set up connections with external systems, you can create new external accounts.

External accounts are used by technical processes such as technical workflows or campaign workflows. For example, when setting up a file transfer in a workflow or a data exchange with any other application (Adobe Target, Experience Manager, etc.), you need to select an external account.

You can access external accounts from Adobe Campaign **[!UICONTROL Explorer]**: browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>A specific **[!UICONTROL Full FDA]** (ffda) external account manages connection between Campaign local database and Cloud database ([!DNL Snowflake]).
>
>As a Managed Cloud Services user, this external account is configured for your instance by Adobe. It must not be modified.


## Campaign-specific external accounts

The following technical accounts are used by Adobe Campaign to enable and execute specific processes.

[!DNL :speech_balloon:] As a Managed Cloud Services user, Adobe configure all Campaign-specific external accounts for you.

* **Bounce mails (POP3)**

    The **Bounce mails** external account specifies the external POP3 account to be used to connect to the email service. All servers configured for POP3 access can be used to receive return mail.

   [!DNL :arrow_upper_right:] Learn more about inbound emails in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/inbound-emails.html)

* **Routing**

    The **[!UICONTROL Routing]** external account allows you to configure each channel available in Adobe Campaign depending on the packages installed.

    >[!CAUTION]
    >
    >The **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) external account **must not** be enabled in Adobe Campaign v8.
    > 

* **Execution instance**

    In the context of transactional messaging, the execution instances is linked to the control instance and connect them. Transactional message templates are deployed to the execution instance.

    [!DNL :bulb:] Learn more about Message Center architecture in [this page](../dev/architecture.md#transac-msg-archi).

## Access to External Systems external accounts 

* **External database (FDA)**

    Use the **External database** type external account to connect to external an database via FDA. 

    External databases compatible with Adobe Campaign v8 are listed in the [Compatibility matrix](../start/compatibility-matrix.md)

    [!DNL :bulb:] Learn more about Federated Data Access (FDA) option in [this section](../connect/fda.md).

## Adobe Solution Integration external accounts

* **Adobe Experience Cloud**

    To connect to the Adobe Campaign console using an Adobe ID, you must configure the **[!UICONTROL Adobe Experience Cloud]** external account.

    [!DNL :bulb:] Learn more about Adobe Identity Management Service (IMS) in [this section](../start/connect.md#connect-ims).

    [!DNL :speech_balloon:] As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to implement Adobe IMS with Campaign.

* **Web Analytics**

    Use the **[!UICONTROL Web Analytics (Adobe Analytics)]** external account to configure data transfer from Adobe Analytics to Adobe Campaign. 

    [!DNL :bulb:] Learn more about Adobe Campaign - Adobe Analytics integration in [this page](../connect/ac-aa.md).

    [!DNL :speech_balloon:] As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Analytics with Campaign.

    * **Adobe Experience Manager**

    The **[!UICONTROL AEM]** external account allows you to manage the content of your email deliveries as well as your forms directly in Adobe Experience Manager.

    [!DNL :bulb:] Learn more about Adobe Campaign - Adobe Analytics integration in [this page](../connect/ac-aem.md).

    [!DNL :speech_balloon:] As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Experience Manager with Adobe Campaign.


## CRM Connector External Accounts 

* **Microsoft Dynamics CRM**

    The **[!UICONTROL Microsoft Dynamics CRM]** external account allows you to import and export Microsoft Dynamics data into Adobe Campaign.
    
    [!DNL :bulb:] Learn more about Adobe Campaign - Microsoft Dynamics CRM integration in [this page](../connect/crm.md).

    With **[!UICONTROL Web API]** deployment type and **[!UICONTROL Password credentials]** authentication, you need to provide the following details:

    * **[!UICONTROL Account]**: Account used to sign in to Microsoft CRM.

    * **[!UICONTROL Server]**: URL of your Microsoft CRM server.

    * **[!UICONTROL Client identifier]**: Client ID which can be found from Microsoft Azure management portal in the **[!UICONTROL Update your code]** category, **[!UICONTROL Client ID]** field.

    * **[!UICONTROL CRM version]**: Version of the CRM between **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** or **[!UICONTROL Dynamics CRM 2016]**.

    With **[!UICONTROL Web API]** deployment type and **[!UICONTROL Certificate]** authentication, you need to provide the following details:

    * **[!UICONTROL Server]**: URL of your Microsoft CRM server.

    * **[!UICONTROL Private Key (Base64 encoded)]**: Private key encoded to Base64

    * **[!UICONTROL Custom Key identifier]**

    * **[!UICONTROL Key ID]**

    * **[!UICONTROL Client identifier]**: Client ID which can be found from Microsoft Azure management portal in the **[!UICONTROL Update your code]** category, **[!UICONTROL Client ID]** field.

    * **[!UICONTROL CRM version]**: Version of the CRM between **[!UICONTROL Dynamics CRM 2007]**, **[!UICONTROL Dynamics CRM 2015]** or **[!UICONTROL Dynamics CRM 2016]**.

* **Salesforce.com**

    The **[!UICONTROL Salesforce CRM]** external account allows you to import and export Salesforce data into Adobe Campaign.

    To configure the Salesforce CRM external account to work with Adobe Campaign, you need to provide the following details:

    * **[!UICONTROL Account]**: Account used to sign in to Salesforce CRM.

    * **[!UICONTROL Password]**: Password used to sign in to Salesforce CRM.

    * **[!UICONTROL Client identifier]**: Learn how to find your client identifier in [this page](https://help.salesforce.com/articleView?id=000205876&type=1).

    * **[!UICONTROL Security token]**: Learn how to find your security token in [this page](https://help.salesforce.com/articleView?id=000205876&type=1).

    * **[!UICONTROL API version]**: Select the version of the API. For this external account, you need to configure you Salesforce CRM with the configuration wizard.

## Transfer Data external accounts

These external accounts can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity.

[!DNL :arrow_upper_right:] Learn more about File transfer in workflows in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/event-activities/file-transfer.html)

* **FTP and SFTP**

    The **FTP** external account lets you configure and test access to a server outside of Adobe Campaign. To set up connections with external systems such as SFTP or FTP servers 898 used for file transfers, you can create your own external accounts.
    To do so, specify in this external account the address and credentials used to establish the connection to the SFTP or FTP server.

* **Amazon Simple Storage Service (S3)**

    The **AWS S3** connector can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity. As you are setting up this new external account, you need to provide the following details:

    * **[!UICONTROL AWS S3 Account Server]**: URL of your server, filled as follows:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

    * **[!UICONTROL AWS access key ID]**: Learn how to find your AWS access key ID in [Amazon documentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys) .

    * **[!UICONTROL Secret access key to AWS]**: Learn how to find your secret access key to AWS in [Amazon documentation](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/).

    * **[!UICONTROL AWS Region]**: Learn more on AWS regions in [Amazon documentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/).

    * The **[!UICONTROL Use server side encryption]** checkbox allows you to store your file in S3 encrypted mode. Learn how to find the access key ID and secret access key in [Amazon documentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys).

* **Azure Blob Storage**

    The **Azure** external account can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity. To configure the **Azure** external account to work with Adobe Campaign, you need to provide the following details:

    * **[!UICONTROL Server]**:  URL of your Azure Blob storage server.

    * **[!UICONTROL Encryption]**: Type of encryption between **[!UICONTROL None]** or **[!UICONTROL SSL]**.

    * **[!UICONTROL Access key]**: Learn how to find your **[!UICONTROL Access key]** in [Microsoft documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).

