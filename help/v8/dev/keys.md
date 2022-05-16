---
title: Key management in Campaign
description: Get started with key management
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
---
# Key management and unicity {#key-management}

In Campaign v8, the primary key is a Universally Unique IDentifier (UUID), which is a string on characters. To create this UUID, the main element of the schema must contain the **autouuid** and **autopk** attributes set to **true**.

Adobe Campaign v8 comes with Snowflake as the core Database. The distributed architecture of the Snowflake database does not provide mechanisms to manage the unicity of a key within a table: end-users are responsible for ensuring consistency of keys within the Adobe Campaign database.

Avoiding duplicates on keys, and especially on primary keys, is mandatory to preserve relational database consistency. Duplicates on primary keys lead to issues with data management workflow activities such as **Query**, **Reconciliation**, **Update data**, and more.

As a best practice, Adobe recommends adopting a [Detect](#detect-duplicates) and [Correct](#correct-duplicates) strategy as part of your overall Data Management process, in case of duplicated keys have been loaded into the database. 

## Detect duplicates{#detect-duplicates}

Campaign comes with a new guardrail which removes automatically any duplicated UUID from an audience during delivery preparation. This new mechanism prevents any error from happening while preparing a delivery. 

>[!CAUTION]
>
>Duplicated keys is not restricted to UUIDs. It can happen in with IDs, including custom keys created in custom tables.

As a end-user, you can check this information in the delivery logs: some recipients can be excluded from the main target because of duplicated key. In that case, the following warning is displayed: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

When this happens, you can create a workflow to identify the duplicate keys. You will then be able to correct these keys. To perform this, follow the steps below:

1. Create a new workflow.

    ![](assets/new-wf.png)
    
1. Add a **Query** activity
1. Select the **Recipient** table

    ![](assets/add-query-on-rcp.png)

1. Add a **Deduplication** activity and deduplicate on the primary key (UUID). Keep just one duplicate and check the  **Generate Complement** option to create an outbound transition for the duplicate(s).

    ![](assets/deduplicate.png)

1. Save the duplicate(s) into a list using a List update activity.

    ![](assets/list-update.png)

Now, you can access the duplicated recipients directly from the list. Even if the transition contains only one of the duplicated rows, all duplicates will be logged into the list.


## Correct duplicates{#correct-duplicates}

Correcting the duplicates requires customers to update Campaign data. The type of action is tightly bound to the nature of the duplicates and the implementation. We can face multiples cases that should require a different mitigation strategy (remove, merge or update).

>[!IMPORTANT]
>
>Duplicated primary keys prevent you from using built-in workflow activities to select or update one specific row. Because of duplicated UUID, data deduplication will fail and can affect your database integrity. As a consequence, it is highly recommended to correct duplicates.

For example:

* **Case 1** -  Duplicated recipients with the same UUID and same profile information (same email, first name, etc.) : the recipients look like "real" duplicates and mitigation could be to just remove one of the duplicates.
Another approach could be to merge information of one recipient into the other.

* **Case 2** - Duplicated recipients with the same UUID but different profile information (different email, first name, etc.):
this time, it seems there are different profiles and you may want to keep both in the Campaign database, which means we may prefer just to update one of the duplicates generating a new UUID. [Learn more in this exemple](#deduplicate-sample).

Depending on your mitigation strategy, you can always query the list from another workflow and then apply the update according to your need. For more guidance, contact Adobe.

### Deduplication sample{#deduplicate-sample}

In case of duplicated recipients, you can keep both records in Campaign database. In that case, you need to update one of them with a new UUID. 

So to run a SQL update query on Cloud Database you can use the **SQL Data Management** workflow activity and execute the following SQL update:

``` sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Once the selected row is updated with a new UUID then you can check the updated row from the interface and notice the UUID has been updated as expected. You can also detect duplicates in the Database by running the **Detect duplicates** workflow [as explained here](#detect-duplicates).
