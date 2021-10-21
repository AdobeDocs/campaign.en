---
title: Understand Campaign Interaction architecture
description: Campaign Interaction Architecture basics
feature: Overview
role: Data Engineer
level: Beginner
---
# Understand Campaign Interaction environments and architecture

## Environments {#environments}

There are two environments for each targeting dimension used when managing offers:

* A **design** environment in which the offer manager takes care of creating and categorizing offers, editing them, and starting the approval process so that they can be used. The rules for each category, the offer spaces on which offers can be presented, and the predefined filters used to define an offer's eligibility are also defined in this environment.

  Categories can also be published manually in the online environment.

  The process for approving offers is detailed [in this section](interaction-offer.md#approve-offers).

* A **live** environment in which approved offers from the design environment, as well as the various offer spaces, filters, categories and rules configured in the design environment can all be found. During a call to the Offer engine, the engine will always use offers from the live environment.

An offer is only deployed on the offer spaces selected during the approval process. Therefore, an offer can be live but unusable on an offer space that is also live.

## Inbound and outbound interactions {#interaction-types}

The Adobe Campaign Interaction module proposes two types of interactions: 

* **inbound** interactions, initiated by a contact. [Learn more](interaction-present-offers.md)
* **outbound** interactions, initiated by a Campaign Delivery manager. [Learn more](interaction-send-offers.md)

These two types of interactions can be carried out either in **unitary mode** (offer is calculated for a single contact), or in **batch mode** (offer is calculated for a set of contacts). Generally, inbound interactions are carried out in unitary mode and outbound interactions are carried out in batch mode. Nevertheless, there may be certain exceptions, for [transactional messages](transactional.md) for example, whereby the outbound interaction is carried out in unitary mode.

As soon as an offer can or must be presented (according to the configurations carried out), the Offer engine plays the intermediary role: it automatically calculates the best possible offer for a contact among those available by combining data received about the contact and the different rules that can be applied as specified in the application.

![](assets/architecture_interaction2.png)

## Distributed architecture

To be able to support scalability and provide 24/7 service on the inbound channel, the **Interaction** module is implemented in a distributed architecture. This type of architecture is already used with [Message Center](../dev/architecture.md#transac-msg-archi) and is made up of several instances:

* one or several control instances dedicated to the outbound channel and containing the marketing and environment design base
* one or several execution instances dedicated to inbound channel

![](assets/interaction_powerbooster_schema.png)

Control instances are dedicated to the inbound channel and contain the online version of the catalog. Every execution instance is independent and dedicated to one contact segment (for example, one execution instance per country). Calls to the Offer engine must be directly performed on the execution (one specific URL per execution instance). As synchronization between instances is not automatic, interactions from the same contact must be sent through the same instance.

### Synchronization {#synchronization}

Offer synchronization is carried out via packages. On execution instances, all catalog objects are prefixed by the external account name. This means several control instances (development and production instances for example) can be supported on one same execution instance.

>[!CAUTION]
>
>Use short and explicit internal names.

Offers are automatically deployed then published on execution and control instances.

Offers deleted in the design environment are disabled on all online instances. Obsolete propositions and offers are automatically deleted on all instances after the purge period (specified in each instance's deployment assistant) and sliding period (specified in the incoming propositions' typology rules).

![](assets/interaction_powerbooster_schema2.png)

A workflow is created for each environment and external account for proposition synchronization. Synchronization frequency can be adjusted for each environment and external account.

You must be aware of the following synchronization mechanisms:

* If you use the fall back function from an anonymous environment to an identified environment, these two environments must be on the same execution instance. 
* The synchronization between several execution instances is not performed in real time. Interactions of the same contact must be sent to the same instance. The control instance must be dedicated to the outbound channel (no real time).
* The marketing database is not automatically synchronized. The marketing data used in the weights and eligibility rules must be duplicated on execution instances. This process does not come as standard, you must develop it during the integration period. 
* Proposition synchronization is carried out exclusively by FDA connection.
* If you use Interaction and Message Center on the same instance, synchronization will occur via FDA protocol in both cases.

### Packages configuration {#packages-configuration}

Any schema extensions directly linked to **Interaction** (offers, propositions, recipients, etc.) must be deployed on the execution instances.

The **Interaction** package is installed on all instances (control and execution). Two additional packages are available: one package for the control instances, and the other for each execution instance.

>[!NOTE]
>
>When installing the package, the **long** type fields of the **nms:proposition** table such as the proposition ID, become **int64** type fields. This type of data is detailed in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data){target="_blank"}.

The data retention duration is configured on each instance (via the **[!UICONTROL Data purge]** window in the deployment wizard). On execution instances, this period must correspond to the historical depth necessary for typology rules (sliding period) and eligibility rules to be calculated.

On the control instances:

1. Create one external account per execution instance:

   ![](assets/interaction_powerbooster1.png)

    * Complete the label and add a short and explicit internal name.
    * Select the **[!UICONTROL Execution instance]**.
    * Check the **[!UICONTROL Enabled]** option.
    * Complete the connection parameters for the execution instance.
    * Every execution instance must be linked to an ID. This ID is assigned when you click on the **[!UICONTROL Initialize connection]** button.
    * Check the type of application used: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]**, or both.
    * Enter the FDA account used. An operator must be created on the execution instances and must have the following read and write rights on the database of the instance in question:

      ```    
      grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
      grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
      ```

   >[!NOTE]
   >
   >The IP address of the control instance must be authorized on the execution instances.

1. Configure the environment:

   ![](assets/interaction_powerbooster2.png)

    * Add the list of execution instances.
    * For each one, specify the synchronization period and filter criteria (for example, by country).

      >[!NOTE]
      >
      >If you encounter an error, you can consult the synchronization workflows and offer notifications. These can be found in the technical workflows of the application.

If, for optimization reasons, only part of the marketing database is duplicated on the execution instances, you can specify a restricted schema linked to the environment to allow the users to only use data that is available on the execution instances. You can create an offer using data that is not available on execution instances. To do this, you must deactivate the rule on the other channels by limiting this rule on the outbound channel (**[!UICONTROL Taken into account if]** field).

![](assets/ita_filtering.png)

### Maintenance options {#maintenance-options}

Here is a list of maintenance options available on the control instance:

>[!CAUTION]
>
>These options must only be used for specific maintenance cases.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: last date that an environment was synced on a given instance.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: last date that propositions from a given schema were synced from one instance to another.
* **`NmsInteraction_MapWorkflowId`**: an option containing the list of all synchronization workflows generated.

The following option is available on execution instances:

**NmsExecutionInstanceId**: option containing the instance ID.

### Packages installation {#packages-installation}

If your instance did not previously have the **Interaction** package, no migration is necessary. By default, the proposition table will be in 64 bits after the packages have been installed.

>[!CAUTION]
>
>Depending on the volume of existing propositions in your instance, this operation may take a while.

* If your instance has little or no propositions, no manual modification of the proposition table is necessary. The modification will be done when packages are installed.
* If your instance has a lot of propositions, it is better to change the structure of the propositions table before installing the control packages and running them. We recommend running the queries during a low-activity period.

>[!NOTE]
>
>If you have carried out specific configurations in the proposition table, adapt the queries accordingly.


There are two methods:

**Work table** (recommended)

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**Alter Table**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```