---
title: Campaign Database mapping
description: Campaign Database mapping
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 0%

---

# Asignación de base de datos{#database-mapping}

The SQL mapping of our example schema gives the following XML document:

```
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

## Descripción {#description}

**`<srcschema>`****`<schema>`**

This takes us to another type of document, which is generated automatically from the source schema, simply referred to as the schema. This schema will be used by the Adobe Campaign application.

The SQL names are determined automatically based on element name and type.

The SQL naming rules are as follows:

* table: concatenation of the schema namespace and name

   ****

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* field: name of the element preceded by a prefix defined according to type (&#39;i&#39; for integer, &#39;d&#39; for double, &#39;s&#39; for string, &#39;ts&#39; for dates, etc.)

   ******`<attribute>`****`<element>`**

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>SQL names can be overloaded from the source schema. To do this, populate the &quot;sqltable&quot; or &quot;sqlname&quot; attributes on the element concerned.

The SQL script to create the table generated from the extended schema is as follows:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

The SQL field constraints are as follows:

* no null values in numeric and date fields,
* numeric fields are initialized to 0.

## XML fields {#xml-fields}

**`<attribute>`****`<element>`** You can, however, reference this field in XML instead of SQL, which means that the data is stored in a memo field (&quot;mData&quot;) of the table containing the values of all XML fields. The storage of these data is an XML document that observes the schema structure.

****

****

* Multi-line comment field:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* Description of data in HTML format:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   The &quot;html&quot; type lets you store the HTML content in a CDATA tag and display a special HTML edit check in the Adobe Campaign client interface.

The use of XML fields lets you add fields without needing to modify the physical structure of the database. Another advantage is that you use less resources (size allocated to SQL fields, limit on the number of fields per table, etc.).

## Administración de claves {#management-of-keys}

A table must have at least one key for identifying a record in the table.

A key is declared from the main element of the data schema.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Keys obey the following rules:

* A key can reference one or more fields in the table.
* ****

**Ejemplo**:

* Adding a key to the e-mail address and city:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="email">
         <keyfield xpath="@email"/> 
         <keyfield xpath="location/@city"/> 
       </key>
   
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
       <element name="location" label="Location">
         <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
       </element>
     </element>
   </srcSchema>
   ```

   The schema generated:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
       <keyfield xpath="@email"/>      
       <keyfield xpath="location/@city"/>    
      </key>    
   
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
      <element label="Location" name="location">      
        <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
      </element>  
     </element>
   </schema>
   ```

* Adding a primary or internal key on the &quot;id&quot; name field:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="id" internal="true">
         <keyfield xpath="@id"/> 
       </key>
   
       <key name="email">
         <keyfield xpath="@email"/> 
       </key>
   
       <attribute name="id" type="long" label="Identifier"/>
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
     </element>
   </srcSchema>
   ```

   The schema generated:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
       <key name="email">      
         <keyfield xpath="@email"/>    
       </key>  
   
       <key internal="true" name="id">      
        <keyfield xpath="@id"/>    
       </key>    
   
       <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
       <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
     </element>
   </schema>
   ```

### Primary key - Identifier{#primary-key}

[](../architecture/enterprise-deployment.md)**** The key value is unique in the entire database. The content of the key is automatically generated on insertion of the record.

**Ejemplo**

Declaring an incremental key in the source schema:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

The schema generated:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

In addition to the definition of the key, a numeric field called &quot;id&quot; has been added to the extended schema in order to contain the auto-generated primary key.

>[!CAUTION]
>
>A record with a primary key set to 0 is automatically inserted on creation of the table. This record is used to avoid outer joins, which are not effective on volume tables. By default, all foreign keys are initialized with value 0 so that a result can always be returned on the join when the data item is not populated.

## Links: relation between tables {#links--relation-between-tables}

A link describes the association between one table and another.

The various types of associations (known as &quot;cardinalities&quot;) are as follows:

* Cardinality 1-1: one occurrence of the source table can have at most one corresponding occurrence of the target table.
* Cardinality 1-N: one occurrence of the source table can have several corresponding occurrences of the target table, but one occurrence of the target table can have at most one corresponding occurrence of the source table.
* Cardinality N-N: one occurrence of the source table can have several corresponding occurrences of the target table, and vice-versa.

In the interface, you can distinguish the different types of relations easily thanks to their icons.

For join relations with a campaign table/database:

* ![](assets/do-not-localize/join_with_campaign11.png) For example, between a recipient and a current order. A recipient can be related to only one occurrence of the current order table at a time.
* ![](assets/do-not-localize/externaljoin11.png) For example, between a recipient and their country. A recipient can be related to only one occurrence of the table country. The content of the country table will not be saved.
* ![](assets/do-not-localize/join_with_campaign1n.png) A recipient can be related to several occurences on the subscriptions table.

For join relations using Federated Database Access:

* ![](assets/do-not-localize/join_fda_11.png)
* ![](assets/do-not-localize/join_fda_1m.png)

![](../assets/do-not-localize/glass.png)[](../connect/fda.md)

A link must be declared in the schema containing the foreign key of the table linked via the main element:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Links obey the following rules:

* ******`<element>`**

   * ****
   * ****
   * ****
   * ****
   * **** Possible values are as follows:

      * ****
      * ****
      * ****
      * ********
      * ****
   * ****
   * ****
   * ****
   * ****


* A link references one or more fields from the source table to the destination table. `<join>`
* A link consists of two half-links, where the first is declared from the source schema and the second is created automatically in the extended schema of the target schema.
* ****

>[!NOTE]
>
>Links are the elements declared at the end of the schema.

### Example 1 {#example-1}

1-N relation to the &quot;cus:company&quot; schema table:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

The schema generated:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

The link definition is supplemented by the fields making up the join, i.e. the primary key with its XPath (&quot;@id&quot;) in the destination schema, and the foreign key with its XPath (&quot;@company-id&quot;) in the schema.

The foreign key is added automatically in an element that uses the same characteristics as the associated field in the destination table, with the following naming convention: name of target schema followed by name of associated field (&quot;company-id&quot; in our example).

Extended schema of the target (&quot;cus:company&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany"  autopk="true" autouuid="true"> 
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

A reverse link to the &quot;cus:recipient&quot; table was added with the following parameters:

* ****
* ****
* ****
* ****
* ****

`autouuid="true"`[](../architecture/enterprise-deployment.md)

### Example 2 {#example-2}

In this example, we will declare a link towards the &quot;nms:address&quot; schema table. The join is an outer join and is populated explicitly with the recipient&#39;s e-mail address and the &quot;@address&quot; field of the linked table (&quot;nms:address&quot;).

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

### Example 3 {#example-3}

1-1 relation to the &quot;cus:extension&quot; schema table:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Example 4 {#example-4}

Link to a folder (&quot;xtk:folder&quot; schema):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

The default value returns the identifier of the first eligible parameter type file entered in the &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot; function.

### Example 5 {#example-5}

****

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

The schema generated:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

The definition of the &quot;companyEmail&quot; name key was extended with the foreign key of the &quot;company&quot; link.
