---
title: Import profiles in Campaign
description: Learn how to import contacts in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Import profiles from a file{#create-profiles}

To populate your Campaign database, you can [add profiles manually](create-profiles.md) or import profiles as detailed below. You can also use imported files to update contact data.

## Import profiles with a workflow {#import-profiles-with-a-wf}

Workflows can be a useful way to automate some of your import processes. Whether you import data from a local file or from a SFTP, you can use workflows to standardize your data management procedures.

### Use data from a list: Read list {#data-from-read-list}

Prepare and structure your data in a file to import it with a workflow. [Learn more](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html){target="_blank"}.

### Load data from a file {#data-from-a-file}

The data processed in a workflow can be extracted from a structured file so that it can be imported into Adobe Campaign. [Learn more](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html){target="_blank"}.

Once data has been collected you can use it in your workflows, for example to enrich a delivery or update the database. For more on this, refer to [this section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html){target="_blank"}.

## One-shot imports{#import-jobs}

Adobe Campaign provides generic import capability which allows you, for example, to extract a list of customers or prospects who will then become part of a target population, or to supply your database with data from external files.

Generic imports are managed from the **[!UICONTROL Profiles and Targets > Jobs]** menu of the Adobe Campaign home page.

![](assets/new-import-job.png)

The steps to perform a generic import are detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html){target="_blank"}.
