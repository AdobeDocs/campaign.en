---
title: Share audiences with Adobe Experience Cloud solutions
description: Learn how to share audiences with Adobe Experience Cloud solutions
feature: Audiences
role: User
level: Beginner
hide: yes
hidefromtoc: yes
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
---
# Share audiences with Adobe Experience Cloud solutions{#shared-audiences}


Option 1: AEP Sources and Destinations

Option 2: Adobe People/AAM

You can integrate **Adobe Campaign** with **People core service** or Adobe Audience Manager. You will then be able to:

* Import shared audiences/segments from different Adobe Experience Cloud solutions into Adobe Campaign. Audiences can be imported via lists in Adobe Campaign.

* Export lists in the form of Adobe Experience Cloud shared audiences. These audiences can be used in the different Adobe Experience Cloud solutions that you use. Audiences can be exported after targeting in a workflow, using a dedicated **[!UICONTROL Update shared audience]** activity.

This integration supports two types of Adobe Experience Cloud IDs:

* **Visitor ID**: this type of identifier reconciles Adobe Experience Cloud visitors with Adobe Campaign recipients.
* **Declared ID**: this type of identifier reconciles all types of data with elements from the Adobe Campaign database. It is represented in Adobe Campaign as a predefined reconciliation key.

    >[!NOTE]
    >
    > Declared ID data source can now also be used with People core service integration.
    >
    >If you are using the People core service integration and want to add the Audience Manager integration, you will need the help of an Adobe Audience Manager consultant's to avoid losing all of the ID syncs collected when transitioning to using this Declared ID data source in an Adobe Audience Manager context.

See:

[Adobe Audience Manager documentation](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html){target="_blank"}

[Adobe Experience Cloud Central Interface Components Guide](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html){target="_blank"}
