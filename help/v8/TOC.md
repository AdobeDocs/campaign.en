---
audience: end-user
user-guide-title: Campaign v8
title: Adobe Campaign v8 Documentation
description: Campaign v8 documentation
breadcrumb-title: Campaign v8
title: Campaign v8 docs
---

# Adobe Campaign v8 documentation {#campaign-v8}

+ [Campaign v8 documentation](campaign-home.md)
+ What's new? {#new}
  + [Key capabilities](start/whats-new.md)
  + [Release notes](start/release-notes.md)
  + [Guardrails](start/ac-guardrails.md)
  + [Known issues](start/known-issues.md)
  + [Classic v7 to v8](start/v7-to-v8.md)
+ Start {#start}
  + [Get started](start/get-started.md)
  + [Components and processes](start/ac-components.md)
  + Campaign UI {#ac-ui}
    + [Discover Campaign interface](start/campaign-ui.md)
    + [Customize Campaign interface](start/customize-ui.md)
  + [Work with audiences](start/audiences.md)
  + [Manage Privacy requests](start/privacy.md)
  + [Import data](start/import.md)
  + [Create campaigns](start/campaigns.md)
  + [Send messages](start/create-message.md)
  + [Manage subscriptions](start/subscriptions.md)
  + [Track & monitor](start/tracking.md)
  + [Metrics & reports](start/reporting.md)
  + [FAQ](start/campaign-faq.md)
+ Architecture {#architecture}
  + [Global principles](architecture/general-architecture.md)
  + [Architecture](architecture/architecture.md)
  + FDA Snowflake deployment {#fda}
    + [What is FDA-Snowflake?](architecture/fda-deployment.md)
  + Enterprise (FFDA) deployment {#ffda}
    + [What is Campaign FFDA?](architecture/enterprise-deployment.md)
    + Characteristics {#ffda-characteristics}
      + [Key management and unicity](architecture/keys.md)
      + [New APIs](architecture/new-apis.md)
      + [API staging mechanism](architecture/staging.md)
      + [Replication mechanism](architecture/replication.md)
+ Implement {#implement}
  + [Implementation steps](start/implement.md)
  + [Customize your instance](dev/customize.md)
  + [Security guidelines](config/security.md)
  + [Design web apps and forms](dev/webapps.md)
  + [Datamodel best practices](dev/datamodel-best-practices.md)
+ Deploy {#deploy}
  + [Compatibility matrix](start/compatibility-matrix.md)
  + [Connect to Campaign](start/connect.md)
  + [Permissions](start/permissions.md)
  + [Control Panel](config/self-service.md)
+ Profiles & Audiences {#profiles-and-audiences}
  + [Get started](audiences/gs-audiences.md)
  + [Access profiles](audiences/view-profiles.md)
  + Add profiles {#add-profiles}
    + [Create profiles manually](audiences/create-profiles.md)
    + [Import profiles from a file](audiences/import-profiles.md)
    + [Work with external profiles](audiences/external-profiles.md)
    + [Collect profile data in web forms](audiences/collect-profiles.md)
  + Create audiences {#create-audiences}
    + [Create a list of contacts](audiences/create-audiences.md)
    + [Create and manage filters](audiences/create-filters.md)
  + [Manage folders and views](audiences/folders-and-views.md)
  + [Best practices](audiences/audiences-best-practices.md)
+ Send messages{#send}
  + Emails {#emails}
    + [Design and validate emails](send/email.md)
    + [Send and monitor emails](send/send.md)
  + [SMS](send/sms.md)
  + [Push notifications](send/push.md)
  + [LINE messaging](send/line.md)
  + [Direct mail](send/direct-mail.md)
  + [Social marketing](send/twitter.md)
  + [Transactional messages](send/transactional.md)
  + Failures, bounces and quarantines{#failures}
    + [Quarantines](send/quarantines.md)
    + [Delivery failures](send/delivery-failures.md)
+ Real-time interaction{#interaction}
  + [Get started with real-time interaction](interaction/interaction.md)
  + [Environments and architecture](interaction/interaction-architecture.md)
  + [Best practices](interaction/interaction-best-practices.md)
  + Define settings{#interaction-settings}
    + [Create operators](interaction/interaction-operators.md)
    + [Create environments](interaction/interaction-env.md)
    + [Create pre-defined filters](interaction/interaction-predefined-filters.md)
    + [Create offer spaces](interaction/interaction-offer-spaces.md)
  + [Create an offer catalog](interaction/interaction-offer-catalog.md)
  + [Create an offer](interaction/interaction-offer.md)
  + [Send an offer (outbound)](interaction/interaction-send-offers.md)
  + Present an offer (inbound){#inbound}
    + [Context](interaction/interaction-present-offers.md)
    + [Call an offer in a web page](interaction/interaction-integration.md)
    + [Manage anonymous interactions](interaction/anonymous-interactions.md)
  + [Reports and history](interaction/interaction-tracking.md)
  + [Use cases](interaction/interaction-use-cases.md)
+ Configure {#config}
  + [Automate with workflows](config/workflows.md)
  + [Email settings](config/email-settings.md)
  + [Transactional messaging settings](config/transactional-msg-settings.md)
  + [Integrate Campaign SDKs with your app](config/push-config.md)
  + [External accounts](config/external-accounts.md)
+ Connect {#connect}
  + [Connect with other solutions](connect/integration.md)
  + [Campaign + Analytics](connect/ac-aa.md)
  + [Campaign + Experience Manager](connect/ac-aem.md)
  + [Campaign + Target](connect/ac-at.md)
  + [Campaign + Experience Cloud triggers](connect/ac-triggers.md)
  + [Campaign + RTCDP](connect/ac-rtcdp.md)
  + [Campaign + Twitter](connect/ac-tw.md)
  + [Campaign + External database](connect/fda.md)
  + Campaign + your CRM {#ac-crm}
    + [Get started with CRM connectors](connect/crm.md)
    + [Work with Campaign and SFDC](connect/ac-sfdc.md)
    + [Work with Campaign and Microsoft Dynamics](connect/ac-ms-dyn.md)
    + [Synchronize data](connect/crm-data-sync.md)
+ Developer resources {#developer}
  + [Campaign datamodel](dev/datamodel.md)
  + Schemas & forms {#shemas-forms}
    + [Work with schemas](dev/schemas.md)
    + [Create schemas](dev/create-schema.md)
    + [Extend schemas](dev/extend-schema.md)
    + [Filter schemas](dev/filter-schema.md)
    + [Schema structure](dev/schema-structure.md)
    + [Database mapping](dev/database-mapping.md)
    + [Restrict PI view](dev/restrict-pi-view.md)
    + [Use a custom recipient table](dev/custom-recipient.md)
    + [Update the database](dev/update-database-structure.md)
    + [Input forms](dev/forms.md)
  + [Campaign APIs](dev/api.md)
+ [Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html)
+ Automation {#automate}
  + Automate with workflows {#automating-with-workflows}
    + Get started with workflows {#introduction}
        + [About workflows](automation/workflow/about-workflows.md)
      + Types of workflows {#wf-type}
        + [Targeting workflows](automation/workflow/targeting-workflows.md)
        + [Campaign workflows](automation/workflow/campaign-workflows.md)
        + [Technical workflows](automation/workflow/technical-workflows.md)
      + [Build a workflow](automation/workflow/build-a-workflow.md)
      + [Best practices](automation/workflow/workflow-best-practices.md)
      + [Use workflow data](automation/workflow/use-workflow-data.md)
    +  Execute a workflow {#executing-a-workflow}
        + [Start a workflow](automation/workflow/start-a-workflow.md)
        + [Workflow life cycle](automation/workflow/workflow-life-cycle.md)
        + [Set up approvals](automation/workflow/define-approvals.md)
    + Monitor workflows {#monitoring-workflows}
        + [Monitor workflow execution](automation/workflow/monitor-workflow-execution.md)
        + [Monitor technical workflows](automation/workflow/monitor-technical-workflows.md)
        + [Workflow HeatMap](automation/workflow/heatmap.md)
    + Workflow activities {#wf-activities}
        + [Get started with activities](automation/workflow/activities.md)
      + Targeting activities {#targeting-activities}
            + [List of targeting activities](automation/workflow/targeting-activities.md)
            + [Cells](automation/workflow/cells.md)
            + [Change data source](automation/workflow/change-data-source.md)
            + [Change dimension](automation/workflow/change-dimension.md)
            + [CRM Connector](automation/workflow/crm-connector.md)
            + [Deduplication](automation/workflow/deduplication.md)
            + [Delivery outline](automation/workflow/delivery-outline.md)
            + [Edit schema](automation/workflow/edit-schema.md)
            + [Enrichment](automation/workflow/enrichment.md)
            + [Exclusion](automation/workflow/exclusion.md)
            + [Incremental query](automation/workflow/incremental-query.md)
            + [Intersection](automation/workflow/intersection.md)
            + [List update](automation/workflow/list-update.md)
            + [Offers by cell](automation/workflow/offers-by-cell.md)
            + [Offer engine](automation/workflow/offer-engine.md)
            + [Query](automation/workflow/query.md)
            + [Read list](automation/workflow/read-list.md)
            + [Split](automation/workflow/split.md)
            + [Subscription Services](automation/workflow/subscription-services.md)
            + [Union](automation/workflow/union.md)
            + [Update data](automation/workflow/update-data.md)
      + Flow control activities {#flow-control-activities}
            + [List of flow control activities](automation/workflow/flow-control-activities.md)
            + [Alert](automation/workflow/alert.md)
            + [AND-join](automation/workflow/and-join.md)
            + [Approval](automation/workflow/approval.md)
            + [External signal](automation/workflow/external-signal.md)
            + [Fork](automation/workflow/fork.md)
            + [Jump (start point and end point)](automation/workflow/jump--start-point-and-end-point-.md)
            + [Start and end](automation/workflow/start-and-end.md)
            + [Scheduler](automation/workflow/scheduler.md)
            + [Sub-workflow](automation/workflow/sub-workflow.md)
            + [Test](automation/workflow/test.md)
            + [Time constraint](automation/workflow/time-constraint.md)
            + [Wait](automation/workflow/wait.md)
      + Action activities {#action-activities}
            + [List of action activities](automation/workflow/action-activities.md)
            + [Content Management](automation/workflow/content-management.md)
            + [Continuous delivery](automation/workflow/continuous-delivery.md)
            + [Cross-channel deliveries](automation/workflow/cross-channel-deliveries.md)
            + [Data extraction (file)](automation/workflow/extraction--file-.md)
            + [Data loading (file)](automation/workflow/data-loading--file-.md)
            + [Data loading (RDBMS)](automation/workflow/data-loading--rdbms-.md)
            + [Delivery](automation/workflow/delivery.md)
            + [Delivery control](automation/workflow/delivery-control.md)
            + [Local approval](automation/workflow/local-approval.md)
            + [Loading (SOAP)](automation/workflow/loading-soap.md)
            + [Nlserver module](automation/workflow/nlserver-module.md)
            + [Recurring delivery](automation/workflow/recurring-delivery.md)
            + [SQL code and JavaScript code](automation/workflow/sql-code-and-javascript-code.md)
            + [SQL Data Management](automation/workflow/sql-data-management.md)
            + [Update aggregate](automation/workflow/update-aggregate.md)
      + Event activities {#event-activities}
            + [List of event activities](automation/workflow/event-activities.md)
            + [File collector](automation/workflow/file-collector.md)
            + [File transfer](automation/workflow/file-transfer.md)
            + [Inbound Emails](automation/workflow/inbound-emails.md)
            + [Inbound SMS](automation/workflow/inbound-sms.md)
            + [Web download](automation/workflow/web-download.md)
    + Use cases {#use-cases}
        + [About workflow use cases](automation/workflow/workflow-use-cases.md)
        + Deliveries {#deliveries}
            + [Use the local approval activity](automation/workflow/local-approval-activity.md)
            + [Send a birthday email](automation/workflow/send-a-birthday-email.md)
            + [Load delivery content](automation/workflow/load-delivery-content.md)
            + [Cross-channel delivery workflow](automation/workflow/cross-channel-delivery-workflow.md)
            + [Email enrichment with custom date fields](automation/workflow/email-enrichment-with-custom-date-fields.md)
        + Monitoring {#monitoring}
            + [Send a report to a list](automation/workflow/send-a-report-to-a-list.md)
            + [Supervise your workflows](automation/workflow/workflow-supervision.md)
            + [Send personalized alerts to operators](automation/workflow/send-alerts-to-operators.md)
        + Data management {#data-management}   
            + [Coordinate data updates](automation/workflow/coordinate-data-updates.md)
            + [Create a summary list](automation/workflow/create-a-summary-list.md)
            + [Enrich data](automation/workflow/enrich-data.md) 
            + [Use aggregates](automation/workflow/using-aggregates.md)
            + [Use the Deduplication activity's merge functionality](automation/workflow/deduplication-merge.md)
            + [Set up a recurring import workflow](automation/workflow/recurring-import-workflow.md)
        + Design queries {#designing-queries}
            + [Quarterly list update using an incremental query](automation/workflow/quarterly-list-update.md)
        + Query and filter {#designing-queries}
            + [Query the recipient table](automation/workflow/querying-recipient-table.md)
            + [Query delivery information](automation/workflow/query-delivery-info.md)
            + [Perform aggregate computing](automation/workflow/compute-aggregates.md)
            + [Query using grouping management](automation/workflow/query-grouping-management.md)
            + [Query using a many-to-many-relationship](automation/workflow/query-many-to-many-relationship.md)
            + [Add an enumeration type calculated field](automation/workflow/adding-enumeration-type-calculated-field.md)
            + [Create a filter](automation/workflow/create-a-filter.md)
            + [Filter duplicated recipients](automation/workflow/filter-duplicated-recipients.md)
    + Advanced settings {#advanced-management}
        + [Workflow properties](automation/workflow/workflow-properties.md)
        + [Advanced parameters](automation/workflow/advanced-parameters.md)
        + [JavaScript scripts and templates](automation/workflow/javascript-scripts-and-templates.md)
        + [Examples of JavaScript code in workflows](automation/workflow/javascript-in-workflows.md)
        + [Access an external database](automation/workflow/accessing-an-external-database--fda-.md)
        + [Manage permissions](automation/workflow/managing-rights.md)
        + [Change activity images](automation/workflow/change-activity-images.md)
        + [Manage time zones](automation/workflow/managing-time-zones.md)
  + Campaign orchestration {#campaign-orchestration}
    + [Get started with marketing campaigns](automation/campaigns/set-up-campaigns.md)
    + [Create programs and campaigns](automation/campaigns/marketing-campaign-create.md)
    + [Create and configure templates](automation/campaigns/marketing-campaign-templates.md)
    + [Add deliveries](automation/campaigns/marketing-campaign-deliveries.md)
    + [Select the audience](automation/campaigns/marketing-campaign-target.md)
    + [Manage documents and assets](automation/campaigns/marketing-campaign-assets.md)
    + [Set up and manage approvals](automation/campaigns/marketing-campaign-approval.md)
    + [Recurring and periodic campaigns](automation/campaigns/recurring-periodic-campaigns.md)
    + [Monitor your campaigns](automation/campaigns/marketing-campaign-monitoring.md)
    + [Providers, stocks and budgets](automation/campaigns/providers--stocks-and-budgets.md)
  + Campaign optimization (add-on){#campaign-optimization}
    + [Get started with campaign typologies](automation/campaign-opt/campaign-typologies.md)
    + [Pressure rules](automation/campaign-opt/pressure-rules.md)
    + [Consistency rules](automation/campaign-opt/consistency-rules.md)
    + [Control rules](automation/campaign-opt/control-rules.md)
    + [Filtering rules](automation/campaign-opt/filtering-rules.md)
    + [Apply rules](automation/campaign-opt/apply-rules.md)
    + [Campaign simulations](automation/campaign-opt/campaign-simulations.md)
  + Distributed marketing (add-on) {#distributed-marketing}
    + [About distributed marketing](automation/distributed-marketing/about-distributed-marketing.md)
    + [Create a local campaign](automation/distributed-marketing/creating-a-local-campaign.md)
    + [Create a collaborative campaign](automation/distributed-marketing/creating-a-collaborative-campaign.md)
    + [Publish the campaign package](automation/distributed-marketing/publishing-the-campaign-package.md)
    + [Access campaigns](automation/distributed-marketing/accessing-campaigns.md)
    + [Track a campaign](automation/distributed-marketing/tracking-a-campaign.md)
    + [Use cases](automation/distributed-marketing/examples.md)

