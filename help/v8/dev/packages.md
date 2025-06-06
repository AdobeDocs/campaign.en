---
title: Working with data packages
description: Working with data packages
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
exl-id: bf1ae889-9c07-4acf-8fd0-55b57151bc47
version: Campaign v8, Campaign Classic v7
---
# Work with data packages{#data-packages}

## Get started with packages {#gs-data-packages}

You can use data packages to export and import your platform custom settings and data. A packags can contain different types of configurations and components, filtered or not. 

In Campaign data packages, entities of the Adobe Campaign database be displayed into XML files. In a package, each entity is represented with all of its data.

The principle of **data packages** is to export a data configuration and integrate it into another Adobe Campaign environment. Learn how to maintain a consistent set of data packages in this [section](#data-package-best-practices).

### Types of packages {#types-of-packages}

You can work with three types of packages in Adobe Campaign: user packages, platform packages, and admin packages.

* A **user package** lets you select the list of entities to be exported. This type of package manages dependencies and checks errors.
* A **platform package** includes all added technical resources (non standard): schemas, JavaScript code, etc. 
* An **admin package** includes all added templates and business objects (non standard): templates, libraries, etc.

>[!CAUTION]
>
>The **platform** and **admin** packages contain a predefined list of entities to be exported. Each entity is linked to filtering conditions that enable you to remove the out-of-the-box resources of the created package.

## Data structure {#data-structure}

The description of a data package is a structured XML document that complies with the grammar of the **xrk:navtree** data schema, as in the example below:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

The XML document must begin and end with the `<package>` element. Any `<entities>` elements that follow distribute the data by document type. An `<entities>` element contains the data of the package in the format of the data schema entered in the **schema** attribute. The data in a package must not contain internal keys that are not compatible between bases, such as auto-generated keys (**autopk** option).

In our example, the joins on the `folder` and `company` links have been replaced by so-called "high level" keys on the destination tables:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

The `operation` attribute with the value `none` defines a reconciliation link.

A data package can be built manually from any text editor. You must ensure that the structure of the XML document complies with the `xtk:navtree` data schema. The client console has a data package export and import module.

## Export packages {#export-packages}

Packages can be exported in three different ways:

* Use the **[!UICONTROL Package Export]** assistant to export a set of objects in a single package. [Learn more](#export-a-set-of-objects-in-a-package)
* To export a **single object**, right-click on it and select **[!UICONTROL Actions > Export in a package]**.
* Use the **Package definitions** to create a package structure in which you add objects to be exported later on in a package. [Learn more](#manage-package-definitions)

Once a package exported, you can import it and all the added entities into another Campaign instance.

### Export a set of objects in a package {#export-a-set-of-objects-in-a-package}

To export a set of objects in a data package, follow these steps:

1. Browse to the package export assistant via the **[!UICONTROL Tools > Advanced > Export package...]** menu of the explorer.
1. Select the [types of packages](#types-of-packages).

    ![](assets/package_type.png)

1. Click the **Add** button to select the entities to export as a package. 

   >[!CAUTION]
   >
   >If you export an **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** or **[!UICONTROL Plan]** type folder, don't ever select the **xtk:folder** as you may lose some data. Select the entity that corresponds with the folder: **nms:offerCategory** for offer categories, **nms:offerEnv** for offer environments, **nms:program** for programs, and **nms:plan** for plans.

    The dependency mechanism controls the entity export sequence. For more on this, refer to [Managing dependencies](#manage-dependencies).

1. Click **[!UICONTROL Next]** and define the filter query on the type of document to be extracted. You must configure the filtering clause for data extraction.

   >[!NOTE]
   >
   >The query editor is presented in [this section](../../automation/workflow/query.md).

1. Click **[!UICONTROL Next]** and select the sort order of exported data.

1. Preview the data to extract to check your configuration.

1. The last page of the package export assistant lets you start the export. The data will be stored in the file indicated in the **[!UICONTROL File]** field.

### Manage dependencies {#manage-dependencies}

The export process tracks the links between the various exported elements. This mechanism is defined by two rules:

* objects linked to a link with an `own` or `owncopy` type integrity are exported in the same package as the exported object.
* objects linked to a link with a `neutral` or `define` type integrity (defined link) must be exported separately.

>[!NOTE]
>
>Integrity types linked to schema elements are defined in [this page](database-links.md).

#### Export a campaign {#export-a-campaign}

Below is an example of how to export a campaign. The marketing campaign to be exported contains:
* a `MyTask`task
* a `campaignWorkflow` workflow in the following folder: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

The task and the workflow are exported in the same package as the campaign since the matching schemas are connected by links with an `own` type integrity.

The package content is:

```xml

<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

Affiliation to a type of package is defined in a schema with the `@pkgAdmin and @pkgPlatform` attribute. Both these attributes receive an XTK expression that defines the conditions of affiliation to the package.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Finally, the `@pkgStatus` attribute enables you to define the export rules for these elements or attributes. Depending on the value of the attribute, the element or attribute will be found in the exported package. The three possible values for this attribute are:

* `never`: does not export the field / link
* `always`: forces export for this field 
* `preCreate`: authorizes creation of the linked entity

>[!NOTE]
>
>The `preCreate` value is only admitted for link type events. It allows you to create or point to an entity that is not yet loaded in the exported package.

## Manage package definitions {#manage-package-definitions}

Package definitions let you create a package structure in which you add entities that will be exported later on in a single package. You will then be able to import this package and all the added entities into another Campaign instance.

### Create a package definition {#create-a-package-definition}

Package definitions can be accessed from the **[!UICONTROL Administration > Configuration > Package management > Package definitions]** menu.

To create a package definition, click the **[!UICONTROL New]** button, then fill in the package definition general information.

![](assets/packagedefinition_create.png)

You can then add entities to the package definition, and export it to an XML file package.

**Related topics:**

* [Add entities to a package definition](#add-entities-to-a-package-definition)
* [Configure package definitions generation](#configure-package-definitions-generation)
* [Export packages from a package definition](#export-packages-from-a-package-definition)

### Add entities to a package definition {#add-entities-to-a-package-definition}

In the **[!UICONTROL Content]** tab, click the **[!UICONTROL Add]** button to select the entities to export with the package. Best practices when selecting entities are presented in the [this section](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Entities can be added to a package definition directly from their location in the instance. To do this, follow the steps below:

1. Right-click the desired entity, then select **[!UICONTROL Actions > Export in a package]**.

1. Select **[!UICONTROL Add to a package definition]**, then select the package definition to which you want to add the entity.

1. The entity is added to the package definition, it will be exported with the package (see [this section](#export-packages-from-a-package-definition)).

### Configure package definitions generation {#configure-package-definitions-generation}

Package generation can be configured from the package definition **[!UICONTROL Content]** tab. To do this, click the **[!UICONTROL Generation parameters]** link.

![](assets/packagedefinition_generationparameters.png)

* Use the **[!UICONTROL Include the definition]** option to include the definition currently used in the package definition.
* Use the **[!UICONTROL Include an installation script]** option to add a javascript script to execute at the package import. When selected, a **[!UICONTROL Script]** tab is added in the package definition screen.
* Use the **[!UICONTROL Include default values]** option to add the values of all the entities' attributes to the package.

    This option is not selected by default, in order to avoid long exports. This means that, by default, entities' attributes with default values ('empty string', '0', and 'false' if not defined otherwise in the schema) are not added to the package and therefore not exported.

  >[!CAUTION]
  >
  >If the instance where the package is imported contains entities that are identical to those of the package (for example with the same external ID), their attributes will not be updated. This can occur if the attributes from the former instance have default values, as they are not included in the package. In that case, selecting the **[!UICONTROL Include default values]** option would prevent versions merging, as all attributes from the former instance would be exported with the package.

### Export packages from a package definition {#export-packages-from-a-package-definition}

To export a package from a package definition, follow the steps below:

1. Select the package definition to export, click the **[!UICONTROL Actions]** button, and select **[!UICONTROL Export the package]**.
1. Check the name and the location of the exported file.
1. Click the **[!UICONTROL Start]** button to launch the export.

## Import packages {#import-packages}

The package import assistant is accessible via the main menu **[!UICONTROL Tools > Advanced > Import package]** of the client console.

### Install a package from a file {#install-a-package-from-a-file}

To import an existing data package, follow these steps:

1. Acess the import assistant via the main menu **[!UICONTROL Tools > Advanced > Import package]** of the client console. 
1. Select the XML file and click **[!UICONTROL Open]**.

The content of the package to be imported is then displayed in the middle section of the editor.

Click **[!UICONTROL Next]** and **[!UICONTROL Start]** to launch the import.

### Install a built-in package {#install-a-standard-package}

Built-in packages (aka. standard packages) are installed when the Adobe Campaign is configured. Depending on your permissions, your deployment model, and your product offering, you can import new standard packages.

Refer to your license agreement to check which packages you can install.

## Data package best practices {#data-package-best-practices}

This section describes how to organize data packages in a consistent way across the life of the project.


### Versions

You must always import within the same version of the platform. You must check that you deploy your packages between two instances that have the same build. Never force the import and always update the platform first (if the build is different).

>[!IMPORTANT]
>
>Importing between different versions is not supported by Adobe.

Pay attention to the schema and database structure. Importing a package with schema must be followed by schema generation.

### Package types {#package-types}

Start by defining different types of packages. Only four types are used:

**Entities** 

* All "xtk" and "nms" specific elements in Adobe Campaign like schemas, forms, folders, delivery templates, etc.
* You can consider an entity as both an "admin" and "platform" element.
* You should not include more than one entity in a package when uploading it on a Campaign instance.  

If you need to deploy your configuration on a new instance, you can import all your entity packages.

**Features**

This type of package:
* Answers a client requirement/specification.
* Contains one or several functionalities.
* Should contain all dependencies to be able to run the functionality without any other package.

**Campaigns**

This package is not mandatory. It is sometimes useful to create a specific type for all campaigns, even if a campaign can been seen as a feature.

**Updates**

Once configured, a feature can be exported into another environment. For example, the package can be exported from a dev environment to a test environment. In this test, a defect is revealed. First, it needs to be fixed on the dev environment. Then, the patch should be applied to the test platform.

The first solution would be to export the whole feature again. But, to avoid any risk (updating unwanted elements), it is safer to have a package containing only the correction.

That's why we recommend creating an "update" package, containing only one entity type of the feature.

An update could not only be a fix, but also a new element of your entity/feature/campaign package. To avoid deploying the whole package, you can export an update package.

### Naming conventions {#data-package-naming}

Now that types are defined, we should specify a naming convention. Adobe Campaign does not allow to create subfolders for package specifications, meaning that numbers is the best solution for staying organized. Numbers prefix package names. 

For example, you can use the following convention:

* Entity: from 1 to 99
* Feature: from 100 to 199
* Campaign: from 200 to 299
* Update: from 5000 to 5999

#### Entity packages order {#entity-packages-order}

To help the import, entity packages should by ordered as they should be imported. 

For example:

* 001 – Schema
* 002 – Form
* 003 – Images
* etc.

>[!NOTE]
>
>Forms should be imported only **after** schema updates.


#### Package documentation {#package-documentation}

When you update a package, you should always put a comment in the description field to detail any modifications and reasons (for example, "add a new schema" or "fix a defect").

Best practice is also to enter the date of the update. 

>[!IMPORTANT]
>
>The description field can only contain up to 2.000 characters.
