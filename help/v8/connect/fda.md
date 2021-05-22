---
solution: Campaign v8
product: Adobe Campaign
title: Work with Campaign and External databases (FDA)
description: Learn how to work with Campaign and External databases
feature: Overview
role: Data Engineer
level: Beginner
---
# Federated Data Access (FDA){#gs-fda}

Use the FDA Connector (Federated Data Access) to connect Campaign to one or more **external databases** and process information stored into them without affecting your Campaign Cloud Database data. You can then access external data without changing the structure of Adobe Campaign data.

>[!NOTE]
>
>Compatible databases for FDA are listed in the [Compatibility matrix](../start/compatibility-matrix.md).

Campaign FDA option allows you to extend your data model in a third-party database. It will automatically detect the structure of the targeted tables and use data from the SQL sources.

Specific **permissions** are required on [!DNL Adobe Campaign] and on the external database to interact together. Learn more in [this section](#fda-permissions).

## Best practices and limitations

* **Optimize email personalization with external data**

    You can pre-process message personalization in a dedicated workflow. To perform this, use the **[!UICONTROL Prepare the personalization data with a workflow]** option, available in the **[!UICONTROL Analysis]** tab of the delivery properties.

    During the delivery analysis, this option automatically creates and executes a workflow that stores all of the data linked to the target in a temporary table, including data from tables linked in an external database.

    This option significantly improves performances when executing the personalization step.

* **FDA limitations**

    The FDA option is made to manipulate the data in external databases in batch mode in workflows. To avoid performance issues, it is not recommended to use the FDA module in the context of unitary operations, such as: personalization, interaction, real-time messaging, etc.

    Avoid the operations that need to use both the Adobe Campaign and the external database as much as possible. To do this, you can:

    * Export the Adobe Campaign database to the external database and execute the operations only from the external database before re-importing the results into Adobe Campaign.

    * Collect the data from the external Adobe Campaign database and execute the operations locally.

    If you want to carry out personalization in your deliveries using data from the external database, collect the data to use in a workflow to make it available in a temporary table. Then use the data from the temporary table to personalize your delivery.

    The FDA option is subject to the limitations of the external database system that you use.


## Configuration steps{#fda-configuration-steps}

To set up access to an external database with FDA, configuration steps are:

1. As an Adobe Managed Services user, contact Adobe to install the drivers on your Campaign instance. 
1. Once drivers are installed, set up the external account that correspond to your database on the Adobe Campaign server and test the external account. [Learn more](#fda-external-account).
1. Create the schema of the external database in Adobe Campaign. This allows you to identify the data structure of the external database. [Learn more](#create-data-schema)
1. If needed, create a new target mapping from the previously created schema. This is required if the recipients of your deliveries come from the external database. This implementation comes with limitations related to message personalization. [Learn more](#define-data-mapping)

## External database external account{#fda-external-account}

You need to create a specific external account to connect your Campaign instance to your external database.

To achieve this, follow the steps below:

1. From Campaign **[!UICONTROL Explorer]**, browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Platform]** `>` **[!UICONTROL External accounts]**.

1. Click **[!UICONTROL New]**.

    >[!NOTE]
    >
    > To be active, the **[!UICONTROL Enabled]** option must be checked. If necessary, uncheck this option to disable access to this database without deleting its configuration.

1. Select **[!UICONTROL External database]** as your external account's **[!UICONTROL Type]**.

1. Choose you external database in the drop-down list and configure the external account. You must specify:

    * **[!UICONTROL Server]**: URL of the server

    * **[!UICONTROL Account]**: Name of the user

    * **[!UICONTROL Password]**: User account password

    * **[!UICONTROL Database]**: Name of the database

        ![](assets/snowflake.png)

1. Click the **[!UICONTROL Parameters]** tab then the **[!UICONTROL Deploy functions]** button to create functions.

1. Once the parameters are entered, click the **[!UICONTROL Test the connection]** button to approve them.

1. To allow Adobe Campaign to access this database, you must deploy the SQL functions. Click the **[!UICONTROL Parameters]** tab then the **[!UICONTROL Deploy functions]** button.

You can define specific work tablespaces for the tables and for the index in the **[!UICONTROL Parameters]** tab.

For [!DNL Snowflake], the connector supports the following options:

| Option   |  Description |
|---|---|
|  workschema | Database schema to use for work tables |
|  warehouse | Name of the default warehouse to use. It will override the user's default. |
|  TimeZoneName |  By default empty, which means that the system time zone of the Campaign Classic app server is used. The option can be used to force the TIMEZONE session parameter. <br>For more on this, refer to [this page](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
|  WeekStart |  WEEK_START session parameter. By default set to 0. <br>For more on this, refer to [this page](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
|  UseCachedResult | USE_CACHED_RESULTS session parameter. By default set to TRUE. This option can be used to disable Snowflake cached results. <br>For more on this, refer to [this page](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |


## Create the data schema{#create-data-schema}

To create the schema of the external database in Adobe Campaign, follow the steps below: 

1. Click the **[!UICONTROL New]** button above the list of data schemas and choose **[!UICONTROL Access external data]**.

    ![](assets/wf_new_schema_fda.png)

1. Enter a name and a description for the schema and select the external account which will enable connection to the database. This enables access to the list of tables available in the external base. Choose the table which contains the data to be collected.

    ![](assets/wf_new_schema_select_table_fda.png)

1. Click **[!UICONTROL OK]** to confirm. Adobe Campaign automatically detects the structure of the selected table and generates the logical schema. Please note that Adobe Campaign does not generate links.

1. Click **[!UICONTROL Save]** to confirm creation.

## Define the taraget mapping{#define-data-mapping}

You can define a mapping on the data in an external table.

To do this, once the schema of the external table has been created, you need to create a new delivery mapping to use the data in this table as a delivery target.

To do this, follow these steps:

1. Browse to **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** > from Adobe Campaign explorer.

1. Create a new target mapping and select the schema you just created as the targeting dimension.

   ![](assets/new-target-mapping.png)


1. Indicate the fields where the delivery information is stored (last name, first name, email, address, etc.).

   ![](assets/wf_new_mapping_define_join.png)

1. Specify the parameters for information storage, including the suffix of the extension schemas in order for them to be easily identifiable.

   ![](assets/wf_new_mapping_define_names.png)

   You can choose whether to store exclusions (**excludelog**), with messages (**broadlog**) or in a separate table.

   You can also choose whether to manage tracking for this delivery mapping (**trackinglog**).

1. Then select the extensions to be taken into account. The extension type depends on your platform's parameters and options (view your license contract).

   ![](assets/wf_new_mapping_define_extensions.png)

   Click the **[!UICONTROL Save]** button to launch delivery mapping creation: all linked tables are created automatically based on the selected parameters.


## Permissions{#fda-permissions}

Specific **permissions** are required on [!DNL Adobe Campaign] and on the external database to interact together.

First, so that the user can carry out operations on an external database via FDA, the operator must have a specific named right in [!DNL Adobe Campaign].

1. Select the **[!UICONTROL Administration > Access Management > Named Rights]** node in the Adobe Campaign explorer.
1. Create a new right by specifying your chosen label.
1. Enter the name of the Named right in the following format **user:base@server**, where :

    * **user** is the name of the user in the external database
    * **base** is the name of the external database
    * **server** is the name of the external database server

1. Save the Named right and link it to your chosen operator from the **[!UICONTROL Administration > Access Management > Operators]** node of the Adobe Campaign explorer.

Then, to process the data contained in an external database, the Adobe Campaign operator must have at least 'Write' permissions on the database to be able to create worktables. These tables are deleted automatically by Adobe Campaign.

The following permissions are necessary:

* **CONNECT**: connection to the remote database
* **READ Data**: read-only access to tables containing customer data
* **READ 'MetaData'**: access to the server data catalogs to obtain the table structure
* **LOAD**: mass loading in work tables (required when working on collections and joins)
* **CREATE/DROP** for **TABLE/INDEX/PROCEDURE/FUNCTION** (only for worktables generated by Adobe Campaign)
* **EXPLAIN** (recommended): for monitoring performances in case of problem
* **WRITE Data** (depending on the integration scenario)

The database administrator needs to make these rights match with the rights specific to each database engine, as detailed below.

| &nbsp;| Snowflake | Amazon Redshift |
|:-:|:-:|:-:|
| **Connecting to remote database**  | USAGE ON WAREHOUSE, USAGE ON DATABASE and USAGE ON SCHEMA privileges  | Creating a user linked to the AWS account  |
| **Creating tables** |  CREATE TABLE ON SCHEMA privilege | CREATE privilege  |
| **Creating indexes** | N/A |  CREATE privilege | 
|  **Creating functions** |  CREATE FUNCTION ON SCHEMA privilege |  USAGE ON LANGUAGE plpythonu privilege to be able to call external python scripts |
| **Creating procedures** | N/A  |  USAGE ON LANGUAGE python privilege to be able to call external python scripts |
| **Removing objects (tables, indexes, functions, procedures)**  |  Owning the object | Owning the object or being a superuser  | 
| **Monitoring executions**  | MONITOR privilege on the required object  |  No privilege required to use EXPLAIN command |
| **Writing data** |  INSERT and/or UPDATE privileges (depending on write operation) | INSERT and UPDATE privileges  |
| **Loading data into tables** |  CREATE STAGE ON SCHEMA, SELECT and INSERT on the target table privileges |  SELECT and INSERT privileges |
| **Accessing to client data**  |  SELECT on (FUTURE) TABLE(S) or VIEW(S) privilege(s) | SELECT privilege  |
| **Accessing to metadata**  | SELECT on INFORMATION_SCHEMA SCHEMA privilege  |  SELECT privilege |


## Use external data in a workflow

Once the data schema is created, data can be processed in Adobe Campaign workflows.

Multiple activities allow you to interact with data from an external database:

* **Filter on external data** -  The **[!UICONTROL Query]** activity allows you to add external data and use it in the defined filter configurations. 

* **Create sub-sets** - The **[!UICONTROL Split]** activity allows you to create sub-sets. You can use external data to define the filtering criteria to use.

* **Load external database** - You can use the external data in the **[!UICONTROL Data loading (RDBMS)]** activity. 

* **Adding information and links** - The **[!UICONTROL Enrichment]** activity lets you to add additional data to the worktable of the workflow, and links to an external table. In this context, it can use data from an external database. 


You can also directly define a connection to an external database from these workflow activities, for a temporary usage. In this case, it will be on a local external database, reserved to be used within a current workflow: it will not be saved on the external accounts. 

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
