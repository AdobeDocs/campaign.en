---
title: Get started with profiles
description: Get started with profiles
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
---
# Import data into Campaign {#ootb-profiles}

Campaign helps you add contacts to the Cloud database. You can load a file, schedule and automate multiple contact updates, collect data on the Web, or enter profile information directly into the recipient table. 

Get started with [audiences](audiences.md)

Understand Campaign [datamodel](../dev/datamodel.md)

## Import profiles in a workflow

Profile imports are configured in dedicated templates executed through workflows via the **Import** activity. They can be repeated automatically according to a schedule, for example to automate data exchange between several information systems. Learn more in [this section](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png) 


## Run unitary imports

Create and execute a generic data import job to load contacts in the Cloud database.

![](assets/new-import.png) 

Learn how to run unitary import jobs to feed your database in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html){target="_blank"}.

## Collect profiles through web apps

Use Campaign to create web forms and collect and manage profile information easily and efficiently. You can share these forms into your website, which makes it easy for your contacts to provide their information. Their information is sent to Campaign to create their profile or update their information if they are already present in the database.

![](assets/web-form-page.png) 

Learn how to create web forms in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html){target="_blank"}.

**Related topics**

* [Create audiences](audiences.md)
* [Deduplicate profiles](../../automation/workflow/deduplication-merge.md)
* [Enrich profile data](../../automation/workflow/enrich-data.md)
