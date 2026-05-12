---
title: Administración de claves en la base de datos de Campaign
description: Comprensión de la administración de claves en esquemas de Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
TQID: https://experienceleague.adobe.com/vXtZ7fdqMhtrJt873qH3hfgTE7pO-SMBnqjCtcriFNQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 1%

---

# Administración de claves {#management-of-keys}

Cada tabla asociada con un esquema de datos debe tener al menos una clave para identificar un registro de una tabla.

Se declara una clave a partir del elemento principal del esquema de datos.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Una clave se conoce como &#39;clave principal&#39; cuando es la primera del esquema que se va a rellenar o si contiene el atributo `internal` establecido como &quot;true&quot;.

Una clave puede hacer referencia a uno o varios campos de la tabla.

**Ejemplo**:

* Añadir una clave a la dirección de correo electrónico y a la ciudad:

  ```sql
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

  El esquema generado:

  ```sql
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

* Adición de una clave principal o interna al campo de nombre &quot;id&quot;:

  ```sql
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

  El esquema generado:

  ```sql
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

## Clave principal: Identificador{#primary-key}

En el contexto de una implementación [empresarial (FDAC)](../architecture/enterprise-deployment.md), la clave principal de las tablas de Adobe Campaign es un **identificador único universal (UUID)** generado automáticamente por el motor de base de datos. El valor clave es único en toda la base de datos. El contenido de la clave se genera automáticamente al insertar el registro.

**Ejemplo**

En el ejemplo siguiente, declaramos una clave incremental en el esquema de origen:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

El esquema generado:

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Además de la definición de la clave, se ha añadido un campo numérico llamado &quot;id&quot; al esquema ampliado para contener la clave principal generada automáticamente.

>[!CAUTION]
>
>Al crear la tabla, se inserta automáticamente un registro con una clave principal establecida en 0. Este registro se utiliza para evitar las uniones externas, que no son efectivas en las tablas de volumen. De forma predeterminada, todas las claves externas se inicializan con el valor 0, de modo que siempre se pueda devolver un resultado en la unión cuando el elemento de datos no se rellena.
