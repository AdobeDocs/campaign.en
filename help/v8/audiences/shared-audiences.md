---
title: Share audiences with Adobe Experience Cloud solutions
description: Learn how to share audiences with Adobe Experience Cloud solutions
feature: Audiences, Profiles
role: User
level: Beginner
hide: yes
hidefromtoc: yes
---
# Share audiences with Adobe Experience Cloud solutions{#shared-audiences}

Option 1: AEP Sources and Destinations

Option 2: Adobe People/AAM

You can integrate **Adobe Campaign** with **People core service** or Adobe Audience Manager. You will then be able to:

* Import shared audiences/segments from different Adobe Experience Cloud solutions into Adobe Campaign. Audiences can be imported via lists in Adobe Campaign.

* Export lists in the form of Adobe Experience Cloud shared audiences. These audiences can be used in the different Adobe Experience Cloud solutions that you use. Audiences can be exported after targeting in a workflow, using a dedicated **[!UICONTROL Update shared audience]** activity.

This integration supports two types of Adobe Experience Cloud IDs:

* **Visitor ID**: this identifier reconciles Adobe Experience Cloud visitors with Adobe Campaign recipients.
* **Declared ID**: this identifier reconciles all types of data with elements from the Adobe Campaign database. It the predefined reconciliation key in Adobe Campaign.

    >[!NOTE]
    >
    > Declared ID data source can also be used with People core service integration.
    >
    >If you are using the People core service integration and want to add the Audience Manager integration, you will need the help of an Adobe Audience Manager consultant’s to avoid losing all of the ID syncs collected when transitioning to using this Declared ID data source in an Adobe Audience Manager context.

See:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en)
