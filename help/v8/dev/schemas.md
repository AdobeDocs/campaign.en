---
solution: Campaign v8
product: Adobe Campaign
title: Work with Campaign schemas
description: Get started with schemas
---
# Work with schemas{#gs-ac-schemas}

The physical and logical structure of the data carried in the application is described in XML. It obeys a grammar specific to Adobe Campaign, called a **schema**.

A schema is an XML document associated with a database table. It defines data structure and describes the SQL definition of the table:

* The name of the table
* Fields
* Links with other tables

It also describes the XML structure used to store data:

* Elements and attributes
* Hierarchy of elements
* Element and attribute types
* Default values
* Labels, descriptions, and other properties.

Schemas enable you to define an entity in the database. There is a schema for each entity.

Adobe Campaign employs Data Schemas to:

* Define how data object within the application are tied to underlying database tables.
* Define links between the different data objects within the Campaign application.
* Define and describe the individual fields included in each object.

For a better understanding of Campaign built-in tables and their interaction, refer to [this section](datamodel.md).

>[!CAUTION]
>
>Some built-in Campaign schemas have an associated schema on the Cloud database. These schemas are identified by the **Xxl** namespace and must not be modified or extended.

## Syntax of schemas {#syntax-of-schemas}

The root element of the schema is **`<srcschema>`**. It contains the **`<element>`** and **`<attribute>`** sub-elements.

The first **`<element>`** sub-element coincides with the root of the entity.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>The root element of the entity has the same name as the schema.

![](assets/schema_and_entity.png)

The **`<element>`** tags define the names of entity elements. **`<attribute>`** tags of the schema define the names of the attributes in the **`<element>`** tags which they have been linked to.

## Identification of a schema {#identification-of-a-schema}

A data schema is identified by its name and its namespace.

A namespace lets you group a set of schemas by area of interest. For example, the **cus** namespace is used for customer-specific configuration (**customers**).

>[!CAUTION]
>
>As a standard, the name of the namespace must be concise and must contain only authorized characters in accordance with XML naming rules.
>
>Identifiers must not begin with numeric characters.

## Reserved namespaces {#reserved-namespaces}

Certain namespaces are reserved for descriptions of the system entities required for the operation of the Adobe Campaign application. The following namespace **must not be used** to identify a new schema, in any upper/lower case combination:

* **xxl**: reserved to Cloud database schemas
* **xtk**: reserved to platform system data
* **nl**: reserved to the overall use of the application
* **nms**: reserved to deliveries (recipient, delivery, tracking, etc.)
* **ncm**: reserved to content management
* **temp**: reserved to temporary schemas
* **crm**: reserved to CRM connectors integration

The identification key of a schema is a string built using the namespace and the name separated by a colon; for example: **nms:recipient**.

## Create or extend Campaign schemas {#create-or-extend-schemas}

To add a field or other element to one of the core data schemas in Campaign, such as the recipient table (nms:recipient), you have to extend that schema. 

[!DNL :bulb:] For more on this, refer to [Extend a schema](extend-schema.md).

To add an entirely new type of data that does not exist in Adobe Campaign (a table of contracts for example) you can create a custom schema directly. 

[!DNL :bulb:] For more on this, refer to [Create a new schema](create-schema.md).

![](assets/schemaextension_1.png)


Once you have created or extended a schema to work in, the best practice is to define its XML content elements in the same order they appear in below.

## Enumerations {#enumerations}

Enumerations are defined first, before the main element of the schema. They allow you to display values in a list in order to restrict the choices that the user has for a given field.

Example:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

When defining fields, you can then use this enumeration like so:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>You can also employ user-managed enumerations (usually under **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) to specify the values for a given field. These are effectively global enumerations, and a better choice if your enumeration may be used outside of the specific schema you are working in.

## Keys {#keys}

Every table must have at least one key, and often it is automatically established in the main element of the schema by using the **@autouuid=true** attribute set to "true".

The primary key can also be defined using the **internal** attribute.

Example:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In this example, instead of letting the **@autouuid** attribute create a default primary key named “id” we are specifying our own “householdId” primary key.

>[!CAUTION]
>
>When creating a new schema or during a schema extension, you need to keep the same primary key sequence value (@pkSequence) for the whole schema.

[!DNL :bulb:] Learn more about keys in [this section](database-mapping.md#management-of-keys).

## Attributes (Fields) {#attributes--fields-}

Attributes allow you to define the fields which make up your data object. You can use the **[!UICONTROL Insert]** button in the schema edition toolbar to drop empty attribute templates into your XML where your cursor is. Learn more in [this section](create-schema.md).

![](assets/schemaextension_2.png)

The full list of attributes is available in the `<attribute>` element section in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Here are some of the more commonly used attributes: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label**, **@length**, **@name**, **@notNull**, **@required**, **@ref**, **@xml**, **@type**.

:[!DNL :arrow_upper_right:]: For more information on each attribute, refer to the Attribute description in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Examples {#examples}

Example of defining a default value:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Example of using a common attribute as a template for a field also marked as mandatory:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Example of a computed field that is hidden using the **@advanced** attribute:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Example of an XML field also stored in an SQL field and which has an **@dataPolicy** attribute.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Although most attributes are linked according to a 1-1 cardinality to a physical field of the database, this is not the case for the XML fields or the computed fields.   
>An XML field is stored in a memo field ("mData") of the table.   
>A computed field however is created dynamically each time a query is started, it therefore only exists in the applicative layer.

## Links {#links}

Links are some of the last elements in the main element of your schema. They define how all of the different schemas in your instance relate to one another.

Links are declared in the schema that contains the **foreign key** of the table to which it is linked.

There are three types of cardinality: 1-1, 1-N, and N-N. It is the 1-N type that is used by default.

### Examples {#examples-1}

An example of a 1-N link between the recipient table (out-of-the-box schema) and a table of custom transactions:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

An example of a 1-1 link between a custom schema "Car" (in the "cus" namespace) and the recipient table:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Example of an external join between the recipient table and a table of addresses based on the email address and not a primary key:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Here "xpath-dst" corresponds to the primary key in the target schema and "xpath-src" corresponds to the foreign key in the source schema.

## Audit trail {#audit-trail}

One useful element you may want to include at the bottom of your schema is a tracking element (Audit trail).

Use the example below to include fields relating to the creation date, the user that created the data, the date, and the author of the last modification for all data in your table:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Updating the database structure {#updating-the-database-structure}

Once your changes are completed and saved, any changes that may impact the SQL structure need to be applied to the database. To do this, use the database update assistant.

![](assets/schemaextension_3.png)

For more on this, refer to [this section](update-database-structure.md).

>[!NOTE]
>
>When modifications do not impact the database structure, you just need to regenerate schemas. To do this, select the schema(s) to update, right click and choose **[!UICONTROL Actions > Regenerate selected schemas...]** .

