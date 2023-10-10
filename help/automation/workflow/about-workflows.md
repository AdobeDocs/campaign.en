---
product: campaign
title: About workflows
description: Automate processes with workflows, manage data and audiences, send messages, and more.
feature: Workflows
role: User
exl-id: 297aa4e3-b672-46b5-9016-5accee8568b8
---
# Get started with workflows{#gs-workflows}

## About workflows{#about-workflows}

Adobe Campaign includes a workflow module that empowers you to orchestrate the full range of processes and tasks across the different modules of the application server. This comprehensive graphical environment lets you design processes including segmentation, campaign execution, file processing, human participation, etc. The workflow engine executes and tracks these processes.

You can use a workflow, for example, to download a file from a server, decompress it, and then import records contained within into the Adobe Campaign database.

A workflow can also involve one or more operators to be notified or who can make choices and approve processes. In this way, it is possible to create a delivery action, assign a task to one or more operators to work on content, specify targets, and to approve proofs before starting the delivery.

Workflows occur within various contexts and stages of the campaign management process.

Adobe Campaign uses workflows to:

* Design targeting workflows. [Learn more](#targeting-workflows)
* Orchestrate cross channel campaigns. [Learn more](#campaign-workflows)
* Perform technical processes, such as cleanup, data tracking collection, calculations, and more. [Learn more](#technical-workflows)

A workflow is a process definition: the workflow diagram, which is a representation of what is supposed to happen. A workflow is also an instance of this process: a workflow instance, which is a representation of what is actually happening.

The workflow template describes the various tasks to be performed and how they are linked together. The task templates are called activities and are represented by icons. They are linked together by transitions.

![](assets/example1.png)

## Key principes

Each workflow contains:

* **[!UICONTROL Activities]**

  An activity describes a task template. The various activities available are represented on the diagram by icons. Each type has common properties and specific properties. For example, while all activities have a name and label, only the **[!UICONTROL Approval]** activity has an assignment.

  In a workflow diagram, a given activity can produce multiple tasks, in particular when there is a loop or recurrent (periodic) actions.

  All workflow activities are listed in [this section](activities.md), including use cases and samples.

* **[!UICONTROL Transitions]**

  Transitions enable you to link activities and to define their sequence. A transition links a source activity to a destination activity. There are several sorts of transitions, which depend on the source activity. Some transitions have additional parameters such as a duration, a condition or a filter.

  A transition which is not linked to a destination activity is colored orange and the arrow head is shown as a diamond.

  >[!NOTE]
  >
  >A workflow containing unterminated transitions can still be executed: a warning message will be generated and the workflow will pause once it reaches the transition but it will not generate an error. It is thus possible to start a workflow without it being finished and to add to it as you go along.

  For more information about how to build a workflow, refer to [this section](build-a-workflow.md).

* **[!UICONTROL Worktables]**

  The worktable contains all the information carried by the transition. Each workflow uses several worktables. The data conveyed in these tables can be accelerated and used throughout the workflow's life cycle, as long as it is not purged. Indeed, unneeded tables are purged each time the workflow is passivated, and possibly during the execution of the largest workflows to avoid overloading the server.

  Learn more on workflow data and tables in [this section](use-workflow-data.md).

## Related sections

Refer to these sections to find guidance and best practices to automate processes with workflows:

* Learn more about workflow activities in [this page](use-workflow-data.md).
* Learn how to build a workflow in [this section](build-a-workflow.md).
* Discover how to use workflows to import data in Campaign in [this section](campaign-workflows.md)..
* Workflow best practices are detailed in [this page](workflow-best-practices.md).
* Find guidance about workflow execution in [this section](start-a-workflow.md).
* Learn how to monitor workflows in [this page](monitor-workflow-execution.md).
* Learn how to grant access to users to use workflows in [this page](managing-rights.md).
