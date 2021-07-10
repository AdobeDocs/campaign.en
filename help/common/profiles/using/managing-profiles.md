---
product: campaign
title: Manage profiles
description: Learn how to manage profiles in Adobe Campaign
audience: platform
content-type: reference
topic-tags: profile-management
exl-id: e1d0556a-6f30-4863-9025-eb9c1b8b53d3
---
# Manage profiles{#managing-profiles}

To access recipient management capabilities, browse the Adobe Campaign tree. To do this, click the **[!UICONTROL Explorer]** button in the toolbar.

By default, recipients are stored in the **[!UICONTROL Profiles and targets]** node of the Adobe Campaign tree. From the same node, you can create one or more folders and sub-folders to store recipient profiles.

The data from each folder must be considered to be partitioned from each other. As a consequence, duplicate management is more complex when working with multiple recipient folders.

>[!NOTE]
>
>To display the list of all recipients in the database, you can create a view. Learn more in [Folders and views](../../access/using/access-management-folders.md).

Once you accessed profiles, you can:

* **Move recipients**: select one or more recipients, drag them from the recipient list, and drop them in the desired folder. A warning message asks you to confirm this action.

* **Copy recipients**: copy one or several recipients in the same folder by selecting them and right-clicking selecting **[!UICONTROL Copy]**.

* **Delete recipients**: best practice to delete recipients is to move them to a specific folder and then purge the content of this folder. It is **strongly recommended not to use** the **[!UICONTROL Delete]** option in this case.

    To purge a folder, use the **[!UICONTROL Actions > Purge folder]** menu, accessed by right-clicking the desired folder.

    ![](assets/s_ncs_user_purge_folder.png)

    Click **[!UICONTROL Start]** to launch the operation. The middle section of the window displays the progress status, as shown below:

    ![](assets/s_ncs_user_purge_folder_start.png)
