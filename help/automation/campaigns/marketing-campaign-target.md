---
product: campaign
title: Marketing campaign target audience
description: Learn how to define the audience of your marketing campaigns
feature: Campaigns, Audiences
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 70a63632-f66d-40f2-806d-bde89303936a
---
# Select the audience of your campaigns {#marketing-campaign-deliveries}

In a marketing campaign, for each delivery, you can define:

* The target audience. You can send messages to a [list of recipient](#send-to-a-group) or build an [audience in a workflow](#build-the-main-target-in-a-workflow)
* A control group. You can [add a control group](#add-a-control-group) to monitor recipients behavior after message delivery
* Seed addresses - Learn more in [this section](../../v8/audiences/test-profiles.md).

Some of this information can be inherited from the [campaign template](marketing-campaign-templates.md#campaign-templates).

<!--
To build the delivery target, you can define filtering criteria for the recipients in the database. This recipient selection mode is presented in [this section](../../delivery/using/steps-defining-the-target-population.md).
-->

## Send to a group{#send-to-a-group}

You can import a population into a list, then target this list in deliveries. To do this, follow the steps below:

1. Edit the delivery and click the **[!UICONTROL To]** link to change the targeted population.
1. In the **[!UICONTROL Main target]** tab, select the **[!UICONTROL Defined via the database]** option and click **[!UICONTROL Add]** to select recipients.

    ![](assets/select-main-target.png)

1. Choose **[!UICONTROL A list of recipients]**.

    ![](assets/target-a-list.png)


1. Click **[!UICONTROL Next]** to select the list.

    ![](assets/select-the-list.png)

    You can refine the target by adding new filtering criteria.

1. Click **[!UICONTROL Finish]** once all criteria are defined, and save the main target.

## Build the audience in a campaign workflow {#build-the-main-target-in-a-workflow}

The main target of a delivery can also be defined in the campaign workflow: this graphical environment lets you build a target using queries, tests and operators: union, deduplication, sharing, etc.

>[!IMPORTANT]
>
>You must not add more than 28 workflows in a campaign. Past this limit, additional workflows are not visible in the interface and can generate errors.

### Create the workflow {#create-a-targeting-workflow}

Targeting can be created via a combination of filtering conditions in a graphical sequence in a workflow. You can create populations and sub-populations which will be targeted according to your requirements. To display the workflow editor, click the **[!UICONTROL Targeting and workflows]** tab in the campaign dashboard.

![](assets/targeting-and-wf-tab.png)

The target population is extracted from the Adobe Campaign database via one or more queries placed in a workflow. Learn how to build a query in [this section](../workflow/query.md).

You can launch queries and share populations via boxes such as Union, Intersection, Sharing, Exclusion, etc.

Select the objects from the lists to the left of the workspace and link them to construct the target.

![](assets/campaign-wf.png)

In the diagram, link up the targeting and scheduling queries required for target construction in the diagram. You can execute the targeting while construction is in progress in order to check the population extracted from the database.

>[!NOTE]
>
>Examples and procedure for defining queries are detailed in [this section](../workflow/query.md).

The left-hand section of the editor contains a library of graphical objects representing activities. The first tab contains the targeting activities, and the second tab contains the flow-control activities, which are used occasionally to coordinate targeting activities.

The targeting workflow execution and formatting functions are accessible via the diagram editor toolbar.

![](assets/wf-diagram.png)

>[!NOTE]
>
>The activities available to build the diagram as well as all display and layout features are detailed in [this section](../workflow/about-workflows.md).

You can create several targeting workflows for a single campaign. To add a workflow:

1. Go to the upper left-hand section of the workflow creation zone, right-click, and select **[!UICONTROL Add]**. You can also use the **[!UICONTROL New]** button located above this zone.

   ![](assets/add-a-wf.png)

1. Select the **[!UICONTROL New workflow]** template and name this workflow.
1. Click **[!UICONTROL OK]** to confirm creation of the workflow, and then create the diagram for this workflow.

### Execute the workflow {#execute-a-workflow}

Targeting workflows can be launched manually via the **[!UICONTROL Start]** button in the toolbar, provided that you have the appropriate rights.

The targeting can be programmed for automatic execution according to a schedule (scheduler) or an event (external signal, file import, etc.).

The actions related to executing the targeting workflow (launch, stop, pause, etc.) are **asynchronous** processes: the command is saved and will take effect as soon as the server is available to apply it.

The toolbar icons let you take action concerning the execution of the targeting workflow.

* Start or restart

    * The **[!UICONTROL Start]** icon lets you launch the targeting workflow. When you click on this icon, all activities without an input transition are activated (except end point jumps).
    
      ![](assets/start.png)

      The server takes the request into account, as shown by its status: **[!UICONTROL Start as soon as possible]**.
    
    * You can restart the targeting workflow via the appropriate toolbar icon. This command may be useful if the **[!UICONTROL Start]** icon is not available, for example when targeting workflow stopping is in progress. In this case, click the **[!UICONTROL Restart]** icon to anticipate the restart. The server takes the request into account, as its status shows: **[!UICONTROL Restart requested]**.
    
* Stop or pause

    * The toolbar icons let you stop or pause a targeting workflow in progress.

      When you click **[!UICONTROL Pause]**, operations in progress **[!UICONTROL are not]** paused, but no other activity is launched until the next restart.
    
      ![](assets/pause.png)

      The server takes the command into account, as its status shows: **[!UICONTROL Pause requested]**.
    
      You can also pause a targeting workflow automatically when its execution reaches a particular activity. To do this, right-click the activity from which targeting workflow is to be paused, and select **[!UICONTROL Enable but do not execute]**. 
    
      ![](assets/donotexecute.png)

      This configuration is shown by a special icon.
    
      ![](assets/pause_activity.png)

      >[!NOTE]
      >
      >This option is useful during advanced targeting campaign design and test phases.

      Click **[!UICONTROL Start]** to resume execution.
    
    * Click the **[!UICONTROL Stop]** icon to stop the execution in progress.
    
      ![](assets/stop.png)

      The server takes the command into account, as its status shows: **[!UICONTROL Stop requested]**.
  
  You can also stop a targeting workflow automatically when the execution reaches an activity. To do this, right-click the activity from which targeting workflow will be stopped, and select **[!UICONTROL Do not activate]**. 

  ![](assets/donotactivate.png)

  This configuration is shown by a special icon.

  ![](assets/unactivation.png)


  >[!NOTE]
  >
  >This option is useful during advanced targeting campaign design and test phases.

* Unconditional stop

  In the Explorer, select **[!UICONTROL Administration > Production > Object created automatically > Campaign workflows]** to access and act on every campaign workflows.

  You can unconditionally stop your workflow by clicking the **[!UICONTROL Actions]** icon and selecting **[!UICONTROL Unconditional]** stop. This action terminates your campaign workflow.

  ![](assets/stop_unconditional.png)

  >[!CAUTION]
  >
  >Unconditional stop is restricted to Admin users. 

## Add a control group {#add-a-control-group}

A control group is a population which will not receive the delivery; it is used to track post-delivery behavior and campaign impact by making a comparison with the behavior of target population, which has received the delivery.

The control group can be extracted from the main target and/or come from a specific group or query.

>[!CAUTION]
>
>You cannot use control groups when loading the target population from an external file.

### Activate the control group for a campaign {#activate-the-control-group-for-a-campaign}

You can define a control group at campaign level, in which case the control group will be applied to each delivery of the campaign concerned.

1. Edit the campaign concerned and click the **[!UICONTROL Edit]** tab.
1. Click **[!UICONTROL Advanced campaign parameters...]**.

   ![](assets/enable-control-group.png)

1. Select the **[!UICONTROL Enable and edit control group configuration]** option.
1. Click **[!UICONTROL Edit...]** to configure the control group.

   ![](assets/edit-control-group.png)

The complete procedure is detailed in [this section](#extract-the-control-group-from-the-main-target). Learn more about control groups in [this section](#add-a-population).

### Activate the control group for a delivery {#activate-the-control-group-for-a-delivery}

You can define a control group at delivery level, in which case the control group will be applied to each delivery of the campaign concerned.

By default, the control group configuration defined at the campaign level applies to every delivery of that campaign. You can, however, adapt the control group for an individual delivery.

>[!NOTE]
>
>If you have defined a control group for a campaign, and you also configure it for a delivery linked to this campaign, only the control group defined for the delivery will be applied.

1. Edit the delivery concerned and then click the **[!UICONTROL To]** link.
1. Click the **[!UICONTROL Control group]** tab and then select **[!UICONTROL Enable and edit control group configuration]**.

   ![](assets/enable-control-group-for-a-delivery.png)

1. Click **[!UICONTROL Edit...]** to configure the control group.

The complete procedure is detailed in [this section](#extract-the-control-group-from-the-main-target).

### Use a new population as a control group {#add-a-population}

You can use a specific population for the control group. In that case, select the list to use as a control group in the related field.

This population can come from a list of recipients or you can define it via a specific query.

![](assets/new-population-as-control-group.png)

>[!NOTE]
>
>Adobe Campaign query editor is presented in [this section](../../v8/start/query-editor.md).

### Extract the control group from the main target {#extract-the-control-group-from-the-main-target}

You can also extract recipients from the main target of the delivery. In this case, recipients will be taken from the target of delivery actions affected by this configuration. This extraction can be random or can be the result of sorting the recipients. 

![](assets/extract-control-group-from-target.png)

To extract a control group, enable the control group for the campaign or delivery and select one of the following options: **[!UICONTROL Activate random sampling]** or **[!UICONTROL Keep only the first records after sorting]**.

* Use the **[!UICONTROL Activate random sampling]** option to apply random sampling to the recipients in the main population. If you then set the threshold to 100, the control group will be made up of 100 recipients selected randomly from the targeted population. The random sampling depends on the database engine. 
* Use the **[!UICONTROL Keep only the first records after sorting]** option to define a limitation based on one or more sorting orders. If you select the **[!UICONTROL Age]** field as a sorting criterion and then define 100 as a threshold, the control group will be made up of the 100 youngest recipients. For instance, it could be interesting to define a control group that includes recipients who make few purchases, or recipients who make frequent purchases, and to compare their behavior with that of the contacted recipients.

Click **[!UICONTROL Next]** to define the sorting order (if necessary) and select the recipient limitation mode.

![](assets/limit-control-group.png)

This configuration is equivalent to a **[!UICONTROL Split]** activity in the workflow, which lets you break the target up into subsets. The control group is one of these subsets. 


### Tutorial video {#create-email-video}

This video explains how to add a control group to a campaign.

>[!VIDEO](https://video.tv.adobe.com/v/335606?quality=12)

Additional Campaign how-to videos are available [here](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
