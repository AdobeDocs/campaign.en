---
title: Create test profiles in Campaign
description: Learn how to create and manage test profiles in Adobe Campaign
feature: Audiences, Profiles
role: User
level: Beginner
---
# Create and manage test profiles {#create-test-profiles}

## What is a seed address? {#gs-seeds}

Test profiles are created as seed addresses. They are used to target recipients who do not match the defined target criteria. Seed addresses let you preview and test the personalization and rendering before sending your delivery, by sending them proofs.

The seed addresses have the following benefits:

* Random substitution of fields with data taken from recipient profiles: this lets you enter only the email address, for instance in the seed address section, and let Campaign automatically fill in the other fields form the profile. Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* When using a workflow with Datamanagement functionalities, the additional data processed in deliveries can be entered at seed address level to force values: this sidesteps random value substitution.
* Seed addresses are automatically excluded from reports on the following delivery statistics: **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]**.

Seed addresses are added to the target of deliveries by being imported or by being created directly in the delivery or the campaign.

>[!NOTE]
>
>Seed addresses are not created in the recipients table, but in a separate table. If you extend the recipients table with new data, you have to extend the seed addresses table as well with the same data. Otherwise, they extended fields will not be taken into account for seed addresses.
>
>An example of how to extend the seed addresses table is presented in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.



## Create seed addresses 

Seed addresses are not managed via standard profiles and targets, but in a dedicated node of the Adobe Campaign explorer: **[!UICONTROL Resources > Campaign management > Seed addresses]**. You can create sub-folders to organize the seed addresses.

Adobe Campaign also lets you create seed address templates which are imported into deliveries or campaigns and adapted based on the specific needs of the concerned deliveries and campaigns. Refer to [Create seed address templates](#creating-seed-address-templates).

### Define addresses {#defining-addresses}

To create seed addresses, follow these steps:

1. Click the **[!UICONTROL New]** button above the list of seed addresses.
1. Enter the data linked to the address in the matching fields from the **[!UICONTROL Recipient]** tab. The available fields correspond to the standard fields in the profiles of the delivery recipients (nms:recipient table): name, first name, email, etc.

   >[!NOTE]
   >
   >The label of the address is automatically filled in with the last name and first name you defined.
   >
   >You do not need to enter all fields of each tab when creating a seed address. Missing personalization elements are entered randomly during delivery analysis.

1. In the **[!UICONTROL Address fields]** tab, enter the values to insert in the delivery logs during the analysis phase, in the **[!UICONTROL nms:broadLog]** table.

1. In the **[!UICONTROL Additional data]** tab, enter the personalization data used for the deliveries created in the Data management workflows and which you want to assign a specific value to. 
    
    Make sure that additional target data has been defined with an alias starting with '@' in the **[!UICONTROL Enrichment]** workflow activity. Otherwise, you will not be able to use them properly with your seed addresses in your delivery activity.

### Create seed address templates {#creating-seed-address-templates}

You can create address templates which can be imported and be modified for each delivery. The process is the same as when defining a new seed address. The only difference is that seed address templates addresses must be stored in a 'Template' type folder.

### Seed addresses for direct mail deliveries {#direct-mail-seed-addresses}

For [direct mail deliveries](../send/direct-mail.md), seed addresses are added during extraction and mixed in the output document.

For direct mail deliveries, the extraction file format must comply with the following limitations:  
 
* It must not use the option **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* If element collections are extracted, these fields will have an empty value for the seed addresses, unless the **[!UICONTROL Single row (expert user)]** option is selected. 

## Add seed addresses in a delivery{#seed-addresses-in-a-delivery}

To add specific seed addresses for a delivery, click the **[!UICONTROL To]** link, then select the **[!UICONTROL Seed addresses]** tab.

There are three possible insertion modes:

1. Enter single seed addresses.  To do this, click the **[!UICONTROL Add]** button and define the content of the address fields. Repeat for each address.

1. Import [seed address templates](#creating-seed-address-template) and adapt them to suit your needs. To do this, click the **[!UICONTROL Import seed templates...]** link and select the folder which contains the address templates.

   If necessary, once they are added, you can double-click them or click the **[!UICONTROL Detail...]** button to adapt the content of each address.

1. Create a condition to dynamically select the control addresses to be inserted. To do this, click the **[!UICONTROL Edit the dynamic condition...]** link, then enter the seed address selection parameters. For instance, you could include all the seed addresses contained in a specific folder, or seed addresses belonging to a specific department from your organization.

   An example of this is presented in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

For deliveries, you can also customize the way addresses are inserted into the extraction file. By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file, or randomly among the recipients of the main target.

## Add seed addresses in a campaign {#seed-addresses-in-a-campaign}

To add seed addresses to a target for a campaign, select the operation and click the **[!UICONTROL Edit]** tab.

Click the **[!UICONTROL Advanced campaign settings...]** link and then the **[!UICONTROL Seed addresses]** tab. The seed addresses inserted from the campaign are added to the target of each delivery in the campaign.

## Seed addresses and custom table {#using-an-external-recipient-table}
 
If the delivery table is an external table, you will need to make additional configurations. The **[!UICONTROL nms:seedmember]** schema must be extended. A tab is added to the seed addresses to define the adequate fields

In this case, to add seed addresses to the delivery, enter the adequate fields directly in the matching tab, or import the address templates.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
 
