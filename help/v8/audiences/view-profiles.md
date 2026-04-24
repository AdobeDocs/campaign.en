---
title: View existing profiles in Campaign
description: Learn how to access contact data in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/KjbdtHFlh5F0wXN2jV9C-sEOY2qry0KuRHhWe9MT9Yk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# View existing profiles {#view-profiles}

Browse to **[!UICONTROL Profiles and targets]** to access recipients stored in Adobe Campaign database. 

From this page, you can [create new recipient](create-profiles.md), edit an existing recipient and access its profile details.

![](assets/profiles-and-targets.png)

For more advanced profile manipulations, access the Campaign tree from the **[!UICONTROL Explorer]** link on the Adobe Campaign home page.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>The built-in Recipient screen is defined through a XML schema and its associated form. The XML schema is stored in the **[!UICONTROL Administration > Configuration > Data schemas]** node of the Adobe Campaign explorer tree. Only expert users may make changes to these schemas.  
>

## Edit a profile {#edit-a-profiles}

Select a profile to display details in a new tab.

![](assets/edit-a-profile.png)

The data concerning profiles is grouped in tabs. These tabs and their content depend on your specific settings and installed packages.

For a typical built-in recipient, you can access the following tabs:

* **[!UICONTROL General]**, for all general profile data. In particular, it contains the last name, first name, email address, email format, etc. 

    This tab also stores the **opt-out** flag for the profile: when the **[!UICONTROL No longer contact (by any channel)]** option is selected, the profile is on denylist. This information is added to the contact data if the recipient clicked on an unsubscription link in a newsletter for example. Such recipient is no longer be targeted on any channel (email, direct mail, etc.). For more on this, refer to [this page](../send/quarantines.md).

* **Contact information**, which contains the direct mail address of the selected profile. 

    You can check in this screen the quality index of the address, and how many errors the address contains. This information is used directly by the direct mail provider, based on the number of errors found during previous deliveries, and cannot be changed manually.

* **Other**, for specific fields which can be personalized and populated depending on your needs. 

    Use the **[!UICONTROL Field properties…]** contextual menu to change the names of the fields and define their format.

    ![](assets/other-tab-field-properties.png)

    Enter the new settings as below:

    ![](assets/change-field-properties.png)

    Check the update in the UI:

    ![](assets/other-tab-updated.png)


    >[!CAUTION]
    >Changes apply to all recipients.
    >


* **Subscriptions**, for all the active subscriptions to services. Use the **History** tab to access details of subscriptions and unsibscriptions for this contact. 

    ![](assets/subscription-tab.png)

    Learn more about Subscriptions [in this section](../start/subscriptions.md).

* **Deliveries**, for all the delivery logs for the selected profile. Use this tab to access the contact's marketing history: labels, dates, and status of all the delivery actions addressed to the profile via all channels.


* **Tracking**, for all the tracking logs for the selected profile. This information is used to track profile behavior following deliveries. This tab shows the cumulative total of all URLs tracked in deliveries. The list is configurable, and usually contains: the URL clicked, date and time of click, and the document that contained the URL

    Learn more about Tracking [in this section](../send/tracking.md).
