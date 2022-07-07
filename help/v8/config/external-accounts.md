---
title: Campaign external accounts
description: Campaign external accounts
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 9634b576-2854-4ea9-ba0d-8efaab2c4aee
---
# Configure your external accounts

Adobe Campaign comes with a set of pre-defined external accounts. In order to set up connections with external systems, you can create new external accounts.

External accounts are used by technical processes such as technical workflows or campaign workflows. For example, when setting up a file transfer in a workflow or a data exchange with any other application (Adobe Target, Experience Manager, etc.), you need to select an external account.

You can access external accounts from Adobe Campaign **[!UICONTROL Explorer]**: browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

![](assets/external-accounts.png)


>[!CAUTION]
>
>In the context of an [Enterprise (FFDA) deployment](../architecture/enterprise-deployment.md), a specific **[!UICONTROL Full FDA]** (ffda) external account manages connection between Campaign local database and Cloud database ([!DNL Snowflake]).
></br>As a Managed Cloud Services user, this external account is configured for your instance by Adobe. It must not be modified.

## Campaign-specific external accounts

The following technical accounts are used by Adobe Campaign to enable and execute specific processes.

![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, Adobe configure all Campaign-specific external accounts for you.

### Bounce mails {#bounce-mails-external-account}

>[!NOTE]
>
>The Microsoft Exchange Online OAuth 2.0 authentication for POP3 capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

The **Bounce mails** external account specifies the external POP3 account to be used to connect to the email service. All servers configured for POP3 access can be used to receive return mail.

Learn more about inbound emails in [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/inbound-emails.html)

![](assets/bounce_external_1.png)

To configure the **[!UICONTROL Bounce mails (defaultPopAccount)]** external account:

* **[!UICONTROL Server]**

  URL of the POP3 server.

* **[!UICONTROL Port]**

  POP3 connection port number. The default port is 110.

* **[!UICONTROL Account]**

  Name of the user.

* **[!UICONTROL Password]**

  User account password.

* **[!UICONTROL Encryption]**

  Type of chosen encryption between **[!UICONTROL By default]**, **[!UICONTROL POP3 + STARTTLS]**, **[!UICONTROL POP3]** or **[!UICONTROL POP3S]**.
    The **Bounce mails** external account specifies the external POP3 account to be used to connect to the email service. All servers configured for POP3 access can be used to receive return mail.

* **[!UICONTROL Function]**

    Inbound email or SOAP router

![](assets/bounce_external_2.png)

>[!IMPORTANT]
>
>Before configuring your POP3 external account using Microsoft OAuth 2.0, you first need to register your application in the Azure portal. For more on this, refer to this [page](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

To configure a POP3 external using Microsoft OAuth 2.0, check the **[!UICONTROL Microsoft OAuth 2.0]** option and fill in the following fields:

* **[!UICONTROL Azure tenant]**

    Azure ID (or Directory (tenant) ID) can be found in the **Essentials** drop-down of your application overview in the Azure portal.

* **[!UICONTROL Azure Client ID]**

    Client ID (or Application (client) ID) can be found in the **Essentials** drop-down of your application overview in the Azure portal.

* **[!UICONTROL Azure Client secret]**:

    Client secret ID can be found in the **Client secrets** column from the **Certificates & secrets** menu of your application in the Azure portal.

* **[!UICONTROL Azure Redirect URL]**:

    Redirect URL can be found in the **Authentication** menu of your application in the Azure portal. It should end with the following syntax `nl/jsp/oauth.jsp`, e.g. `https://redirect.adobe.net/nl/jsp/oauth.jsp`.

After entering your different credentials, you can click **[!UICONTROL Setup the connection]** to finish your external account configuration.

### Routing {#routing}

The **[!UICONTROL Routing]** external account allows you to configure each channel available in Adobe Campaign depending on the packages installed.

>[!CAUTION]
>
>The **[!UICONTROL Internal email delivery routing]** (defaultEmailBulk) external account **must not** be enabled in Adobe Campaign v8.

### Execution instance {#execution-instance}

In the context of transactional messaging, the execution instances is linked to the control instance and connect them. Transactional message templates are deployed to the execution instance.

![](../assets/do-not-localize/glass.png) Learn more about Message Center architecture in [this page](../architecture/architecture.md#transac-msg-archi).

## Access to External Systems external accounts 

* **External database (FDA)**

    Use the **External database** type external account to connect to external an database via FDA. 

    External databases compatible with Adobe Campaign v8 are listed in the [Compatibility matrix](../start/compatibility-matrix.md)

    ![](../assets/do-not-localize/glass.png) Learn more about Federated Data Access (FDA) option in [this section](../connect/fda.md).

## Adobe Solution Integration external accounts

* **Adobe Experience Cloud**

    The **[!UICONTROL Adobe Experience Cloud]** external account is used implement Adobe IMS to connect to the Adobe Campaign console using an Adobe ID.

    ![](../assets/do-not-localize/glass.png) Learn more about Adobe Identity Management Service (IMS) in [this section](../start/connect.md#connect-ims).

* **Web Analytics**

    Use the **[!UICONTROL Web Analytics (Adobe Analytics)]** external account to configure data transfer from Adobe Analytics to Adobe Campaign. 

    ![](../assets/do-not-localize/glass.png) Learn more about Adobe Campaign - Adobe Analytics integration in [this page](../connect/ac-aa.md).

    ![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Analytics with Campaign.

    * **Adobe Experience Manager**

    The **[!UICONTROL AEM]** external account allows you to manage the content of your email deliveries as well as your forms directly in Adobe Experience Manager.

    ![](../assets/do-not-localize/glass.png) Learn more about Adobe Campaign - Adobe Analytics integration in [this page](../connect/ac-aem.md).

    ![](../assets/do-not-localize/speech.png)  As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to integrate Adobe Experience Manager with Adobe Campaign.


## CRM Connector External accounts 

* **Microsoft Dynamics CRM**

    The **[!UICONTROL Microsoft Dynamics CRM]** external account allows you to import and export Microsoft Dynamics data into Adobe Campaign.
    
    ![](../assets/do-not-localize/glass.png) Learn more about Adobe Campaign - Microsoft Dynamics CRM integration in [this page](../connect/ac-ms-dyn.md).

* **Salesforce.com**

    The **[!UICONTROL Salesforce CRM]** external account allows you to import and export Salesforce data into Adobe Campaign.

    ![](../assets/do-not-localize/glass.png) Learn more about Adobe Campaign - Salesforce.com CRM integration in [this page](../connect/ac-sfdc.md).

## Transfer Data external accounts

These external accounts can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity.

Learn more about File transfer in workflows in [this page](https://experienceleague-review.corp.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/file-transfer.html)

* **FTP and SFTP**

    The **FTP** external account lets you configure and test access to a server outside of Adobe Campaign. To set up connections with external systems such as SFTP or FTP servers 898 used for file transfers, you can create your own external accounts.
    To do so, specify in this external account the address and credentials used to establish the connection to the SFTP or FTP server.

* **Amazon Simple Storage Service (S3)**

    The **AWS S3** connector can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity. As you are setting up this new external account, you need to provide the following details:

    * **[!UICONTROL AWS S3 Account Server]**: URL of your server, filled as follows:   ```<S3bucket name>.s3.amazonaws.com/<s3object path>```

    * **[!UICONTROL AWS access key ID]**: Learn how to find your AWS access key ID in [Amazon documentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

    * **[!UICONTROL Secret access key to AWS]**: Learn how to find your secret access key to AWS in [Amazon documentation](https://aws.amazon.com/fr/blogs/security/wheres-my-secret-access-key/){target="_blank"}.

    * **[!UICONTROL AWS Region]**: Learn more on AWS regions in [Amazon documentation](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/){target="_blank"}.

    * The **[!UICONTROL Use server side encryption]** checkbox allows you to store your file in S3 encrypted mode. Learn how to find the access key ID and secret access key in [Amazon documentation](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys){target="_blank"}.

* **Azure Blob Storage**

    The **Azure** external account can be used to import or export data to Adobe Campaign using a **[!UICONTROL Transfer file]** workflow activity. To configure the **Azure** external account to work with Adobe Campaign, you need to provide the following details:

    * **[!UICONTROL Server]**:  URL of your Azure Blob storage server.

    * **[!UICONTROL Encryption]**: Type of encryption between **[!UICONTROL None]** or **[!UICONTROL SSL]**.

    * **[!UICONTROL Access key]**: Learn how to find your **[!UICONTROL Access key]** in [Microsoft documentation](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal){target="_blank"}.
