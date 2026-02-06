---
title: Work with Campaign and External databases (FDA)
description: Learn how to work with Campaign and External databases
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
---
# Federated Data Access (FDA){#gs-fda}

Use the FDA Connector (Federated Data Access) to connect Campaign to one or more **external databases** and process information stored into them without affecting your Campaign Cloud Database data. You can then access external data without changing the structure of Adobe Campaign data.

>[!NOTE]
>
>* Compatible databases for Federated Data Access are listed in the [Compatibility matrix](../start/compatibility-matrix.md).
>
>* In the context of an [Enterprise (FFDA) deployment](../../v8/architecture/enterprise-deployment.md), a specific external account is available to manage communication between Campaign local database and Snowflake cloud database. This external account is set up for you by Adobe and **must not** be modified.
>
>* As a Managed Cloud Services user, [contact Adobe](../start/campaign-faq.md#support) to connect your external database(s) with Campaign.


## Best practices and limitations

The FDA option is subject to the limitations of the third-party database system that you use.

In addition, be aware of the following limitations and best practices:

* The FDA option is made to manipulate the data in external databases in batch mode in workflows. To avoid performance issues, it is not recommended to use the FDA module in the context of unitary operations, such as: personalization, interaction, real-time messaging, etc.

* Avoid the operations that need to use both the Adobe Campaign and the external database as much as possible. To do this, you can:

    * Export the Adobe Campaign database to the external database and execute the operations only from the external database before re-importing the results into Adobe Campaign.

    * Collect the data from the external Adobe Campaign database and execute the operations locally.

    If you want to carry out personalization in your deliveries using data from the external database, collect the data to use in a workflow to make it available in a temporary table. Then use the data from the temporary table to personalize your delivery. To perform this, pre-process message personalization in a dedicated workflow using the **[!UICONTROL Prepare the personalization data with a workflow]** option, available in the **[!UICONTROL Analysis]** tab of the delivery properties. During the delivery analysis, this option automatically creates and executes a workflow that stores all of the data linked to the target in a temporary table, including data from tables linked in an external database.
    
    >[!CAUTION]
    >
    >This option significantly improves performances when executing the personalization step.


## Use external data in a workflow

Campaign comes with several workflow activities you can use to interact with data from your external database(s):

* **Filter on external data** -  Use the **[!UICONTROL Query]** activity to add external data and use it in the defined filter configurations. 

* **Create sub-sets** - Use the **[!UICONTROL Split]** activity to create sub-sets. You can use external data to define the filtering criteria to use.

* **Load external database** - Use the external data in the **[!UICONTROL Data loading (RDBMS)]** activity. 

* **Adding information and links** - Use the **[!UICONTROL Enrichment]** activity to add additional data to the worktable of the workflow, and links to an external table. In this context, it can use data from an external database. 

You can also directly define a connection to an external database from all the workflow activities listed above, for a temporary usage. In this case, it will be on a local external database, to be used only within the current workflow.

>[!CAUTION]
>
>This type of configuration must only be used temporary to collect data. The external account configuration should be preferred for any other usage.

For example, in the **[!UICONTROL Query]** activity, you can define a temporary connection to an external database as follows:

1. Open the activity and click the **[!UICONTROL Add data...]**
1. Select the **[!UICONTROL External data]** options
1. Select the **[!UICONTROL Locally defining the data source]** option
1. Select the target database engine in the drop-down list. Enter the name of the server and provide the authentication parameters. Also specify the name of the external database.
1. Select the table where the data is stored. You can enter the name of the table directly in the corresponding field or click the edit icon to access the list of the database tables.
1. Click the **[!UICONTROL Add]** button to define one or several reconciliation fields between the external database data and the data in the Adobe Campaign database. The **[!UICONTROL Edit expression]** icons of the **[!UICONTROL Remote field]** and **[!UICONTROL Local field]** gives you access to the list of fields of each of the tables.
1. If necessary, specify a filtering condition and the data sorting mode.
1. Select the additional data to be collected in the external database. To do this, double click on the fields(s) that you want to add to display them in the **[!UICONTROL Output columns]**. 
1. Click **[!UICONTROL Finish]** to confirm this configuration.
