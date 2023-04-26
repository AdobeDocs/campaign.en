---
title: Work with Campaign and SFDC
description: Learn how to work with Campaign and Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
---
# Work with Campaign and SFDC{#crm-sfdc}

Learn how to configure Campaign CRM connector to connect Campaign v8 to **Salesforce.com**.

Once configuration is done, data synchronization between systems is carried out via a dedicated workflow activity. [Learn more](crm-data-sync.md).

>[!NOTE]
>
>Supported SFDC versions are detailed in Campaign [Compatibility matrix](../start/compatibility-matrix.md).

Follow the steps below to configure a dedicated external account to import and export Salesforce data into Adobe Campaign. 

## Create the connection{#new-sfdc-external-account}

First, you must create the Salesforce external account.

1. Browse the **[!UICONTROL Administration > Platform > External accounts]** node of the Campaign explorer and create an external account.
1. Select **[!UICONTROL Salesforce.com]** external account in the **Type** section.
1. Enter settings to enable connection.
    
    ![](assets/sfdc-external-account.png)

    To configure the Salesforce CRM external account to work with Adobe Campaign, you need to provide the following details:

    * Enter your Salesforce login in the **[!UICONTROL Account]** field.
    * Enter your Salesforce password.
    * You can ignore the **[!UICONTROL Client identifier]** field.
    * Copy/paste your Salesforce **[!UICONTROL Security token]**
    * Select your **[!UICONTROL API version]**. Supported SFDC API versions are listed in Campaign [Compatibility matrix](../start/compatibility-matrix.md).

1. Select the **Enable** option to activate the account in Campaign.

>[!NOTE]
>
>To approve the setup, you need to log off and back on to the Adobe Campaign console.

## Select tables to synchronize{#sfdc-create-tables}

You can now configure tables to synchronize.

1. Click the **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Select the tables to synchronize and start the process.
1. Check the schema generated in Adobe Campaign in the **[!UICONTROL Administration > Configuration > Data schemas]** node.

   Example of a **Salesforce** schema imported in Campaign:

   ![](assets/sfdc-schemas.png)

## Synchronize enumerations{#sfdc-enum-sync}

Once the schema is created, you can synchronize enumerations automatically from Salesforce to Adobe Campaign.

1. Open the assistant from the  **[!UICONTROL Synchronizing enumerations...]** link. 
1. Select the Adobe Campaign enumeration that matches the Salesforce enumeration. 
    You can replace all values of an Adobe Campaign enumeration with those of the CRM: to do this, select **[!UICONTROL Yes]** in the **[!UICONTROL Replace]** column.

   ![](assets/sfdc-enum.png)

1. Click **[!UICONTROL Next]** and then **[!UICONTROL Start]** to start importing the enumerations.

1. Browse the **[!UICONTROL Administration > Platform > Enumerations]** node to check imported values. Learn more about enumerations in [this page](../config/ui-settings.md#enumerations).

Adobe Campaign and Salesforce.com are now connected. You can set up data synchronization between the two systems. 

To synchronize data between Adobe Campaign data and SFDC, create a workflow and use the **[!UICONTROL CRM connector]** activity.

Learn more about data synchronization [in this page](crm-data-sync.md).
