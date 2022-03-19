---
title: View existing profiles in Campaign
description: Learn how to access contact data in Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
---
# View existing profiles{#view-profiles}

Browse to **[!UICONTROL Profiles and targets]** to access recipients stored in Adobe Campaign database. 

From this page, you can create new recipient, edit an existing recipient and access its profile details.

For more advanced profile manipulations, access the Campaign tree from the **[!UICONTROL Explorer]** link on the Adobe Campaign home page.

By default, recipients are stored in the **[!UICONTROL Profiles and Targets > Recipients]** node of the tree. You can create recipients from this view. 

![](assets/profiles-and-targets.png)


## Edit a profile{#edit-a-profiles}

Select a profile to display details in a new tab.

![](assets/edit-a-profile.png)

The data concerning profiles is grouped in tabs. These tabs and their content depend on your specific settings and installed packages.

For a typical built-in recipient, you can access the following tabs:

* **[!UICONTROL General]**, for all general profile data. In particular, it contains the last name, first name, email address, email format, etc. 

    This tab also stores the **opt-out** flag for the profile: when the **[!UICONTROL No longer contact (by any channel)]** option is selected, the profile is on denylist. This information is added to the contact data if the recipient clicked on an unsubscription link in a newsletter for example. Such recipient is no longer be targeted on any channel (email, direct mail, etc.). For more on this, refer to [this page](../../delivery/using/understanding-quarantine-management.md).

## Contact information tab {#contact-information-tab}

This screen contains the direct mail address of the selected profile. It looks like this:

![](assets/s_ncs_user_profile_details_tab.png)

This screen shows the quality index of the address, as well as how many errors the address contains. This information is used directly by the mail carrier based on the number of errors found during previous deliveries, and is not modifiable manually.

>[!CAUTION]
>
>The XML schema and the form that concerns the fields in the profiles table are accessed via the **[!UICONTROL Administration > Configuration > Data schemas]** node of the Adobe Campaign tree. Only expert users may make changes to these schemas.  
>
>For further information, refer to [this page](../../configuration/using/about-schema-edition.md).


## Active profiles {#active-profiles}

Active profiles are the profiles that are counted for billing purposes.

Billing only concerns profiles that are **active**. A profile is considered active if the profile has been targeted or communicated with in the past 12 months via any channel.

A profile that has been targeted by several deliveries is counted only once.

Active profiles count is available for **Marketing instances** only. It is not available for Execution instances, meaning MID (mid sourcing) and RT (Message Center / Real-time messaging) instances.

>[!NOTE]
>
>You can also monitor the number of active profiles on your instance directly from Campaign Control Panel. For more on this, refer to the [Control Panel documentation](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
