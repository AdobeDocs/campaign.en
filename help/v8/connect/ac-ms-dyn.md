---
title: Work with Campaign and Microsoft Dynamics
description: Learn how to work with Campaign and Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
---
# Work with Campaign and Microsoft Dynamics 365{#crm-ms-dynamics}

Activate your CRM data on cross-channel communication: learn how to pass on contacts from **Microsoft Dynamics 365** to Adobe Campaign, and share campaign performance data (sends, opens, clicks, and bounces) back from Adobe Campaign to Microsoft Dynamics 365.

Once configuration is done, data synchronization between systems is carried out via a dedicated workflow activity. [Learn more](crm-data-sync.md).

>[!NOTE]
>
>Supported Microsoft Dynamics versions are detailed in Campaign [Compatibility matrix](../start/compatibility-matrix.md).

Follow the steps below to configure a dedicated external account to import and export Microsoft Dynamics 365 data into Adobe Campaign. 

For each system, these steps need to be performed by an administrator.

>[!CAUTION]
> Steps in this documentation will guide you through creating integrations/registrations that involve assigning permissions and/or admin access. It is your responsibility to ensure these steps comply with your company policies before performing, and to perform them carefully.

## Configure Microsoft Dynamics 365 {#config-crm-microsoft}

To connect Microsoft Dynamics 365 to work with Adobe Campaign via **Web API**, log on to [Microsoft Azure Directory](https://portal.azure.com) using a **Global administrator** credential, and follow the steps below:

1. Get your Dynamics 365 Application (client) ID. [Learn more](#get-client-id-microsoft)
1. Generate Microsoft Dynamics Certificate key identifier and Key ID. [Learn more](#config-certificate-key-id)
1. Configure permissions. [Learn more](#config-permissions-microsoft)
1. Create an App User. [Learn more](#create-app-user-microsoft)
1. Encode the private key. [Learn more](#configure-acc-for-microsoftt)


### Get Dynamics 365 Client ID {#get-client-id-microsoft}

To get the Application (client) ID, you need to register an App in Azure Active Directory. 

1. Browse to **Azure Active Directory > App Registrations**, and select **New Registration**.
1. Enter a unique name which can help identify an instance, such as **adobecampaign`<instance identifier>`**.

Once you save, Microsoft Azure Directory assigns a unique **Application (client) ID** to your app. You will need this ID later on in configuring Dynamics 365 in Adobe Campaign.

Learn more in [Microsoft Dynamics 365 documentation](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### Generate Microsoft Dynamics Certificate key identifier and Key ID {#config-certificate-key-id}

To get the **Certificate key identifier (customKeyIdentifier)** and the **Key ID (keyId)**, you must upload a certificate. Certificates can be used as secrets to prove the application’s identity when requesting a token. Also can be referred to as public keys.

Follow the steps below:

1. Browse to **Azure Active Directory > App Registrations** and select the Application which was created earlier.
1. Select on **Certificates & Secret**.
1. From the **Certificates** tab, click on **Upload certificate**
1. Upload your public certificate.
1. Browse to the **Manifest** link to get the **Certificate key identifier (customKeyIdentifier)** and the **Key ID (keyId)**.

The **Certificate key identifier (customKeyIdentifier)** and the **Key ID (keyId)** are needed in Campaign to configure your Microsoft Dynamics 365 CRM external account using the Certificate **[!UICONTROL CRM O-Auth type]**.

+++ How to generate the public certificate

To generate the certificate, you can use openssl.

For example:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>You can change the number of days, here `-days 365`, in the code sample for a longer certificate validity period.

You must then encode the certificate in base64. To do so, you can use the help of a Base64 encoder or use the command line `base64 -w0 private.key` for Linux.

+++

### Configure permissions {#config-permissions-microsoft}

**Step 1**: Configure the **Required Permissions** for the app that was created.

1. Navigate to **Azure Active Directory > App Registrations** and select the Application which was created earlier.
1. Click **Settings** on the top left.
1. On **Required Permissions**, click **Add** and **Select an API > Dynamics CRM Online**.
1. Click **Select**, enable **Access Dynamics 365 as organization users** checkbox and click **Select**.
1. Then, from your app, select the **Manifest** under the **Manage** menu.
1. From the **Manifest** editor, set the `allowPublicClient` property from `null` to `true` and click **Save**.

**Step 2**: Grant admin consent

1. Navigate to **Azure Active Directory > Enterprise applications**.
1. Select the application to which you want to grant tenant-wide admin consent.
1. From the left pane menu, select **Permissions** under **Security**.
1. Click **Grant admin consent**.

For more information on this, refer to [Azure documentation](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Create an App User {#create-app-user-microsoft}

>[!NOTE]
>
> This step is optional with **[!UICONTROL Password credentials]** authentication.

The App user is the user that the application registered above will use. Any changes made to Microsoft Dynamics using the App registered above will be done via this user.

**Step 1**: Create a non-interactive user on azure active directory

1. Click **Azure Active Directory > Users** and click **New User**.
1. Give a proper name that you want use and the username should be an email format.
1. Choose **Dynamics 365 Administrator** in the **Directory Role**.

**Step 2**:  Assign a proper license to the created user

1. From [Microsoft Azure](https://portal.azure.com), click on **Admin app**.
1. Go to **Users > Active Users** and click on the newly created user.
1. Click on **Edit product licenses** and select the **Dynamics 365 Customer Engagement Plan**.
1. Click **Close**.

**Step 3**: Create an application user on Dynamics CRM

1. From [Microsoft Azure](https://portal.azure.com), navigate to **Settings > Security > Users**.
1. Click on drop-down, select **Application users**, and click **New**.
1. Use the same username as the user created on active directory above.
1. Assign the **Application ID** for [the application you created earlier](#get-client-id-microsoft).
1. Click on **Manage Roles** and choose the **System administrator** role to the user.

## Configure Campaign {#configure-acc-for-microsoft}

### Create the connection{#new-ms-dyn-external-account}

First, you must create the Microsoft Dynamics 365 external account.

1. Browse the **[!UICONTROL Administration > Platform > External accounts]** node of the Campaign explorer and create an external account.
1. Select **[!UICONTROL Microsoft Dynamics CRM]** external account in the **Type** section.
1. Select the authentication method in the **[!UICONTROL CRM O-Auth type]** drop-down list.
    
    ![](assets/ms-dyn-external-account.png)

    1. To configure the Microsoft Dynamics CRM external account to connect with Adobe Campaign with **Password Credentials**, provide the following details:

        * **Server**: URL of your Microsoft CRM server. To find your Microsoft CRM Server URL, access your Microsoft Dynamics CRM account then click Dynamics 365 and select your app. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
        * **Account**: Account used to sign in to Microsoft CRM.
        * **Password**: Account used to sign in to Microsoft CRM.
        * **Client identifier**: Application (client) ID which can be found from Microsoft Azure management portal in the Update your code category, Client ID field.
        * **CRM version**: Choose Dynamics CRM 365 CRM version.

    1. To configure the Microsoft Dynamics CRM external account to connect with Adobe Campaign with a **Certificate**, provide the following details:

        * **Server**: URL of your Microsoft CRM server. To find your Microsoft CRM Server URL, access your Microsoft Dynamics CRM account then click Dynamics 365 and select your app. You can then find your Server URL in the address bar of your browser, e.g. https://myserver.crm.dynamics.com/.
        * **Private key**: Copy/Paste the private key, encoded base64 as explained in [this section](#config-certificate-key-id).
        * **Key ID**: Key available in the **Manifest** tab of your application, as explained in [this section](#config-certificate-key-id).
        * **Custom Key identifier**: Identifier available in the **Manifest** tab of your application, as explained in [this section](#config-certificate-key-id).
        * **Client identifier**: Application (client) ID which can be found from Microsoft Azure management portal as explained in [this section](#get-client-id-microsoft).
        * **CRM version**: Choose Dynamics CRM 365 CRM version.

1. Select the **Enable** option to activate the account in Campaign.

>[!NOTE]
>
>To approve the setup, log off and back on to the Adobe Campaign Client Console.

### Select tables to synchronize{#ms-dyn-create-tables}

You can now configure tables to synchronize.

1. Click the **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. Select the tables to synchronize and start the process.
1. Check the schema generated in Adobe Campaign in the **[!UICONTROL Administration > Configuration > Data schemas]** node.

>[!NOTE]
>
>Make sure to add to the allowlist two URLs: the server URL and `login.microsoftonline.com`. To perform this, contact your Adobe representative.

## Synchronize enumerations{#sfdc-enum-sync}

Once the schema is created, you can synchronize enumerations automatically from Dynamics 365 to Adobe Campaign.

1. Open the assistant from the  **[!UICONTROL Synchronizing enumerations...]** link. 
1. Select the Adobe Campaign enumeration that matches the Dynamics 365 enumeration. 
    You can replace all values of an Adobe Campaign enumeration with those of the CRM: to do this, select **[!UICONTROL Yes]** in the **[!UICONTROL Replace]** column.
1. Click **[!UICONTROL Next]** and then **[!UICONTROL Start]** to start importing the enumerations.
1. Browse the **[!UICONTROL Administration > Platform > Enumerations]** node to check imported values.

Adobe Campaign and Microsoft Dynamics 365 are now connected. You can set up data synchronization between the two systems. 

To synchronize data between Adobe Campaign data and Microsoft CRM, create a workflow and use the **[!UICONTROL CRM connector]** activity.

Learn more about data synchronization [in this page](crm-data-sync.md).

### Supported field data types {#ms-dyn-supported-types}

For Microsoft Dynamics 365 supported/unsupported attribute types are listed below:


| Attribute  type                                                                   | Supported |
| --------------------------------------------------------------------------------- | --------- |
| Basic types : boolean, datetime, decimal, float, double, integer, bigint , string | Yes       |
| Money (as double)                                                                 | Yes       |
| memo, entityname , primarykey, uniqueidentifier (as strings)                      | Yes       |
| Status, picklist (we store the possible values in enumerations), state (string)   | Yes       |
| owner (as string)                                                                 | Yes       |
| Lookup (only single entity reference lookups)                                     | Yes       |
| customer                                                                          | No        |
| Regarding                                                                         | No        |
| PartyList                                                                         | No        |
| ManagedProperty                                                                   | No        |
