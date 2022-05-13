---
title: Work with Campaign schemas
description: Get started with schemas
exl-id: 87af72fe-6c84-4d9a-afed-015900890cce
source-git-commit: 355b9219ffd9d481d15d2d0982d49923842cc27b
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 7%

---

# Usar esquemas{#gs-ac-schemas}

La estructura física y lógica de los datos que se llevan en la aplicación se describe en XML. ****

A schema is an XML document associated with a database table. It defines data structure and describes the SQL definition of the table:

* The name of the table
* Campos
* Links with other tables

It also describes the XML structure used to store data:

* Elementos y atributos
* Hierarchy of elements
* Element and attribute types
* Valores predeterminados
* Labels, descriptions, and other properties.

Schemas enable you to define an entity in the database. There is a schema for each entity.

Adobe Campaign employs Data Schemas to:

* Define how data object within the application are tied to underlying database tables.
* Definir vínculos entre los diferentes objetos de datos dentro de la aplicación de Campaign.
* Definir y describir los campos individuales incluidos en cada objeto.

[](datamodel.md)

>[!CAUTION]
>
>Some built-in Campaign schemas have an associated schema on the Cloud database. ****

## Syntax of schemas {#syntax-of-schemas}

**`<srcschema>`** **`<element>`****`<attribute>`**

**`<element>`**

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

**`<element>`** **`<attribute>`****`<element>`**

## Identification of a schema {#identification-of-a-schema}

A data schema is identified by its name and its namespace.

A namespace lets you group a set of schemas by area of interest. ********

>[!CAUTION]
>
>As a standard, the name of the namespace must be concise and must contain only authorized characters in accordance with XML naming rules.
>
>Identifiers must not begin with numeric characters.

## Reserved namespaces {#reserved-namespaces}

Certain namespaces are reserved for descriptions of the system entities required for the operation of the Adobe Campaign application. ****

* ****
* ****
* ****
* ****
* ****
* ****
* ****

****

## Create or extend Campaign schemas {#create-or-extend-schemas}

To add a field or other element to one of the core data schemas in Campaign, such as the recipient table (nms:recipient), you have to extend that schema.

![](../assets/do-not-localize/glass.png)[](extend-schema.md)

To add an entirely new type of data that does not exist in Adobe Campaign (a table of contracts for example) you can create a custom schema directly.

![](../assets/do-not-localize/glass.png)[](create-schema.md)

![](assets/schemaextension_1.png)


Once you have created or extended a schema to work in, the best practice is to define its XML content elements in the same order they appear in below.

## Enumeraciones {#enumerations}

Enumerations are defined first, before the main element of the schema. They allow you to display values in a list in order to restrict the choices that the user has for a given field.

Ejemplo:

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
>**[!UICONTROL Administration]****[!UICONTROL Platform]** These are effectively global enumerations, and a better choice if your enumeration may be used outside of the specific schema you are working in.

<!--
## Index {#index} 

In the context of a [FDA Snowflake deployment](../architecture/fda-deployment.md), you need to declare indexes. Indexes are the first elements declared in the main element of the schema. 

They can be unique or not, and reference one or more fields.

Examples:

```
<dbindex name="email" unique="true">
  <keyfield xpath="@email"/>
</dbindex>
```

```
<dbindex name="lastNameAndZip">
  <keyfield xpath="@lastName"/>
  <keyfield xpath="location/@zipCode"/>
</dbindex>
```

The **xpath** attribute points to the field in your schema that you wish to index.

>[!IMPORTANT]
>
>It is important to remember that the SQL query read performance gains provided by indexes also come with a performance hit on writing records. The indexes should therefore be used with precaution.

For more on indexes, refer to the [Indexed fields](database-mapping.md#indexed-fields) section.

-->

## Keys {#keys}

********

[](../architecture/enterprise-deployment.md)********

****

Ejemplo:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

********

>[!CAUTION]
>
>Al crear un nuevo esquema o durante una ampliación de esquema, se debe mantener el mismo valor de secuencia de clave principal (@pkSequence) para todo el conjunto.

![](../assets/do-not-localize/glass.png)[](database-mapping.md#management-of-keys)

## Attributes (Fields) {#attributes--fields-}

Attributes allow you to define the fields which make up your data object. **[!UICONTROL Insert]** Obtenga más información en [esta sección](create-schema.md).

![](assets/schemaextension_2.png)

`<attribute>`[](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model) ********************************************************

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic)

### Ejemplos {#examples}

Example of defining a default value:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Example of using a common attribute as a template for a field also marked as mandatory:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

****

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

****

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Although most attributes are linked according to a 1-1 cardinality to a physical field of the database, this is not the case for the XML fields or the computed fields.\
>An XML field is stored in a memo field (&quot;mData&quot;) of the table.\
>A computed field however is created dynamically each time a query is started, it therefore only exists in the applicative layer.

## Vínculos {#links}

Links are some of the last elements in the main element of your schema. They define how all of the different schemas in your instance relate to one another.

****

There are three types of cardinality: 1-1, 1-N, and N-N. It is the 1-N type that is used by default.

### Ejemplos {#examples-1}

An example of a 1-N link between the recipient table (out-of-the-box schema) and a table of custom transactions:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

An example of a 1-1 link between a custom schema &quot;Car&quot; (in the &quot;cus&quot; namespace) and the recipient table:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Example of an external join between the recipient table and a table of addresses based on the email address and not a primary key:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Here &quot;xpath-dst&quot; corresponds to the primary key in the target schema and &quot;xpath-src&quot; corresponds to the foreign key in the source schema.

## Pista de auditoría {#audit-trail}

One useful element you may want to include at the bottom of your schema is a tracking element (Audit trail).

Use the example below to include fields relating to the creation date, the user that created the data, the date, and the author of the last modification for all data in your table:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Actualización de la estructura de la base de datos {#updating-the-database-structure}

Once your changes are completed and saved, any changes that may impact the SQL structure need to be applied to the database. To do this, use the database update assistant.

![](assets/schemaextension_3.png)

Para obtener más información, consulte [esta sección](update-database-structure.md).

>[!NOTE]
>
>When modifications do not impact the database structure, you just need to regenerate schemas. **[!UICONTROL Actions > Regenerate selected schemas...]**
