---
title: Create profile audiences in Campaign
description: Learn how to create lists and build an audience
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
---
# Create an audience in a list {#create-segments}

Use Campaign lists to create and organize your audiences.

A list is a static set of contacts which can be targeted in delivery actions or updated during an import or another workflow action. For example, a population extracted from the database via a query can be stored as a list.

Lists are created and managed via the **[!UICONTROL Lists]** link in the **[!UICONTROL Profiles and targets]** tab. These list are based on the default Adobe Campaign profile table (nms:recipient). [Learn more](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

You can create a list using the **Update list** activity in a workflow. This activity stores the resulting population into a list. Use it to create a new list or update an existing list. To create lists containing other types of data than the built-in profile table, you must run a workflow. For example, by using a query on the visitor table then updating the list, you can create a visitor list. [Learn more](#create-a-list-wf).

Watch this video to learn more about Lists management in Adobe Campaign.

>[!VIDEO](https://video.tv.adobe.com/v/334909?quality=12)


## Create a list of contacts {#create-a-list-of-contacts}

To create a list of contacts, follow the steps below: 

1. Click the **[!UICONTROL Create]** button and select **[!UICONTROL New list]**.
    
    ![](assets/new-list.png)

1. Enter the information in the **[!UICONTROL Edit]** tab of the list creation window.
   
   ![](assets/list-details.png)

    * Enter the list name in the **[!UICONTROL Label]** field and, if necessary, change the internal name.
    * Add a description for this list.
    * You can specify an expiration date: when this date is reached, the list is purged and automatically deleted.
    

1. In the **[!UICONTROL Content]** tab, click **[!UICONTROL Add]** to select the profiles belonging to the list.

   ![](assets/add-profiles-to-a-list.png)

   You can create a new profile and add it in the list directly from this window using the **[!UICONTROL Create]** icon. The profile will be added to the database.

1. Click **[!UICONTROL Save]** to save the list. It is then added to the overview of lists.


## Convert filtered contacts to a list {#convert-data-to-a-list}

You can select profiles and add them to a list. To perform this, follow the steps below:

1. From Campaign Explorer, select profiles and right-click.
   
   These profiles can be filtered to met specific criteria.
   
1. Select **[!UICONTROL Actions > Associate selection with a list...]**.

   ![](assets/add-selection-to-a-list.png)

1. Select an existing list or create a new list, and click **[!UICONTROL Next]**.

   ![](assets/select-the-list.png)

1. Click the **[!UICONTROL Start]** button.

   ![](assets/record-a-list.png)

Select the **[!UICONTROL Recreate the list]** option to delete the existing content from the list and optimize the creation of the list (no query is needed to verify whether the profiles are already linked to the list).

If you uncheck the **[!UICONTROL No trace of this job is saved in the database]** option, you can select (or create) the execution folder where the information linked to this process will be stored.

The upper section of the window lets you monitor execution. The **[!UICONTROL Stop]** button lets you stop the process. Contacts already processed will be linked to the list.

Once the execution is finished, access the **[!UICONTROL Profiles and Targets > Lists]** menu and select the list: the **[!UICONTROL Content]** tab shows the profiles linked to this list.


## Create a list with a workflow  {#create-a-list-wf}

You can use the **[!UICONTROL List update]** activity to create a list or add a population to a list of recipients.

In the example below, you create a list of all the recipients between 25 and 40. 

1. Select **[!UICONTROL Profiles and targets]**, and **[!UICONTROL Targeting workflows]**, then create a new workflow from the **[!UICONTROL Create]** button.
1. Enter a label for this workflow, for example '25-40 contacts', add a description, and click **[!UICONTROL Next]**.

   ![](assets/targeting-wf-sample.png)

1. Insert a **[!UICONTROL Query]** activity to define the target population, and edit the query.

   ![](assets/targeting-wf-edit-query.png)

1. Define the filter conditions, as below:

   ![](assets/targeting-wf-age-filter.png)

   Learn how to create a query in a workflow in [this section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. Add a label for this query and save your changes.
1. Add a **[!UICONTROL List update]** activity, and edit it.

   ![](assets/list-update-activity.png)

1. Enter a label for the activity.
1. Select the **[!UICONTROL Create the list if necessary (Computed name)]** option to show that the list will be created once the first workflow has been executed, then updated with the following executions.
1. Select a folder and enter a label for the list. 
1. Select the **[!UICONTROL Database of the targeting dimension]** to store the table.
1. Leave the **[!UICONTROL Purge the list if it exists (otherwise add to the list)]** option checked to delete recipients that do not match the targeting criteria, and to insert the new ones into the list.
1. Also leave the **[!UICONTROL Create or use a list with its own table]** option checked.
1. Leave the **[!UICONTROL Generate an outbound transition]** option unchecked.
1. Click **[!UICONTROL Ok]**, and save the workflow.
1. Start the workflow.

   The list of matching recipients is then created. You can access to this list from the **[!UICONTROL Lists]** entry of the home page.

   ![](assets/access-new-list.png)

   You can make this workflow recurrent by adding a scheduler to the workflow. [Learn more](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html){target="_blank"}.

## Remove a profile from a list {#remove-a-profile-from-a-list}

To remove a profile from a list, edit the list, select the profile in the **[!UICONTROL Content]** tab, then click the **[!UICONTROL Delete]** icon.

## Delete a list of profiles {#delete-a-list-of-profiles}

To delete a list, browse to it from Campaign Explorer, select it and right-click. Choose **[!UICONTROL Delete]**. A warning message asks you to confirm the deletion.

>[!NOTE]
>
>When you delete a list, the profiles on the list are not affected but the data in their profile is updated.
