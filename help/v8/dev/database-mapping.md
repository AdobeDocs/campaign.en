---
title: Campaign Database mapping
description: Campaign Database mapping
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
---
# Database mapping{#database-mapping}

The SQL mapping of our example schema gives the following XML document:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Description {#description}

The root element of the schema is no longer **`<srcschema>`**, but **`<schema>`**.

This takes us to another type of document, which is generated automatically from the source schema, simply referred to as the schema. This schema will be used by the Adobe Campaign application.

The SQL names are determined automatically based on element name and type.

The SQL naming rules are as follows:

* table: concatenation of the schema namespace and name

  In our example, the name of the table is entered via the main element of the schema in the **sqltable** attribute:

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* field: name of the element preceded by a prefix defined according to type ('i' for integer, 'd' for double, 's' for string, 'ts' for dates, etc.)

  The field name is entered via the **sqlname** attribute for each typed **`<attribute>`** and **`<element>`**:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>SQL names can be overloaded from the source schema. To do this, populate the "sqltable" or "sqlname" attributes on the element concerned.

The SQL script to create the table generated from the extended schema is as follows:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

The SQL field constraints are as follows:

* no null values in numeric and date fields
* numeric fields are initialized to 0

## XML fields {#xml-fields}

By default, any typed **`<attribute>`** and **`<element>`** element is mapped onto an SQL field of the data schema table. You can, however, reference this field in XML instead of SQL, which means that the data is stored in a memo field ("mData") of the table containing the values of all XML fields. The storage of these data is an XML document that observes the schema structure.

To populate a field in XML, you must add the **xml** attribute with the value "true" to the element concerned.

**Examples**

* Multi-line comment field:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Description of data in HTML format:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  The "html" type lets you store the HTML content in a CDATA tag and display a special HTML edit check in the Adobe Campaign client interface.

The use of XML fields lets you add fields without needing to modify the physical structure of the database. Another advantage is that you use less resources (size allocated to SQL fields, limit on the number of fields per table, etc.).
