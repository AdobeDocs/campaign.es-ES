---
title: Asignación de base de datos de Campaign
description: Asignación de base de datos de Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Asignación de base de datos{#database-mapping}

La asignación SQL del esquema de ejemplo proporciona el siguiente documento XML:

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

## Descripción {#description}

El elemento raíz del esquema ya no es **`<srcschema>`**, pero **`<schema>`**.

Esto nos lleva a otro tipo de documento, que se genera automáticamente a partir del esquema de origen, simplemente denominado esquema. La aplicación Adobe Campaign utilizará este esquema.

Los nombres SQL se determinan automáticamente en función del nombre y el tipo del elemento.

Las reglas de nomenclatura SQL son las siguientes:

* tabla: concatenación del área de nombres y el nombre del esquema.

  En este ejemplo, el nombre de la tabla se introduce mediante el elemento principal del esquema en **sqltable** atributo:

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* field: nombre del elemento precedido por un prefijo definido según el tipo (&quot;i&quot; para entero, &quot;d&quot; para doble, &quot;s&quot; para cadena, &quot;ts&quot; para fechas, etc.)

  El nombre del campo se introduce mediante la variable **sqlname** para cada uno de los **`<attribute>`** y **`<element>`**:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>Los nombres SQL se pueden sobrecargar desde el esquema de origen. Para ello, rellene los atributos &quot;sqltable&quot; o &quot;sqlname&quot; en el elemento correspondiente.

La secuencia de comandos SQL para crear la tabla generada a partir del esquema ampliado es la siguiente:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

Las restricciones de campo SQL son las siguientes:

* no hay valores nulos en los campos numérico y de fecha
* los campos numéricos se inicializan en 0

## Campos XML {#xml-fields}

De forma predeterminada, cualquier **`<attribute>`** y **`<element>`** se asigna a un campo SQL de la tabla de esquema de datos. Sin embargo, puede hacer referencia a este campo en XML en lugar de en SQL, lo que significa que los datos se almacenan en un campo memo (&quot;mData&quot;) de la tabla que contiene los valores de todos los campos XML. El almacenamiento de estos datos es un documento XML que observa la estructura del esquema.

Para rellenar un campo en XML, debe añadir la variable **xml** con el valor &quot;true&quot; al elemento correspondiente.

**Ejemplos**

* Campo de comentarios multilínea:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Descripción de los datos en formato HTML:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  El tipo &quot;html&quot; permite almacenar el contenido del HTML en una etiqueta CDATA y mostrar una comprobación especial de edición del HTML en la interfaz de cliente de Adobe Campaign.

El uso de campos XML permite añadir campos sin necesidad de modificar la estructura física de la base de datos. Otra ventaja es que utiliza menos recursos (tamaño asignado a campos SQL, límite en el número de campos por tabla, etc.).
