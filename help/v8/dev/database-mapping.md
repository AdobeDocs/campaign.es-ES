---
title: Asignación de base de datos de Campaign
description: Asignación de base de datos de Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 0%

---

# Asignación de base de datos{#database-mapping}

La asignación SQL del esquema de ejemplo proporciona el siguiente documento XML:

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

El elemento raíz del esquema ya no es **`<srcschema>`**, pero **`<schema>`**.

Esto nos lleva a otro tipo de documento, que se genera automáticamente a partir del esquema de origen, simplemente denominado esquema. La aplicación Adobe Campaign utilizará este esquema.

Los nombres SQL se determinan automáticamente en función del nombre y el tipo del elemento.

Las reglas de nomenclatura SQL son las siguientes:

* tabla: concatenación del área de nombres y el nombre del esquema.

  En este ejemplo, el nombre de la tabla se introduce mediante el elemento principal del esquema en **sqltable** atributo:

  ```
  <element name="recipient" sqltable="CusRecipient">
  ```

* field: nombre del elemento precedido por un prefijo definido según el tipo (&quot;i&quot; para entero, &quot;d&quot; para doble, &quot;s&quot; para cadena, &quot;ts&quot; para fechas, etc.)

  El nombre del campo se introduce mediante la variable **sqlname** para cada uno de los **`<attribute>`** y **`<element>`**:

  ```
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>Los nombres SQL se pueden sobrecargar desde el esquema de origen. Para ello, rellene los atributos &quot;sqltable&quot; o &quot;sqlname&quot; en el elemento correspondiente.

La secuencia de comandos SQL para crear la tabla generada a partir del esquema ampliado es la siguiente:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

Las restricciones de campo SQL son las siguientes:

* no hay valores nulos en los campos numérico y de fecha,
* los campos numéricos se inicializan en 0.

## Campos XML {#xml-fields}

De forma predeterminada, cualquier **`<attribute>`** y **`<element>`** se asigna a un campo SQL de la tabla de esquema de datos. Sin embargo, puede hacer referencia a este campo en XML en lugar de en SQL, lo que significa que los datos se almacenan en un campo memo (&quot;mData&quot;) de la tabla que contiene los valores de todos los campos XML. El almacenamiento de estos datos es un documento XML que observa la estructura del esquema.

Para rellenar un campo en XML, debe añadir la variable **xml** con el valor &quot;true&quot; al elemento correspondiente.

**Ejemplo**: estos son dos ejemplos de uso de campos XML.

* Campo de comentarios multilínea:

  ```
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Descripción de los datos en formato HTML:

  ```
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  El tipo &quot;html&quot; permite almacenar el contenido del HTML en una etiqueta CDATA y mostrar una comprobación especial de edición del HTML en la interfaz de cliente de Adobe Campaign.

El uso de campos XML permite añadir campos sin necesidad de modificar la estructura física de la base de datos. Otra ventaja es que utiliza menos recursos (tamaño asignado a campos SQL, límite en el número de campos por tabla, etc.).

## Administración de claves {#management-of-keys}

Una tabla debe tener al menos una clave para identificar un registro de la tabla.

Se declara una clave a partir del elemento principal del esquema de datos.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Las claves obedecen las siguientes reglas:

* Una clave puede hacer referencia a uno o varios campos de la tabla.
* Una clave se conoce como &#39;primary&#39; (o &#39;priority&#39;) cuando es la primera del esquema que se rellena o si contiene la variable **interno** con el valor &quot;true&quot;.

**Ejemplo**:

* Añadir una clave a la dirección de correo electrónico y a la ciudad:

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

  El esquema generado:

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

* Adición de una clave principal o interna al campo de nombre &quot;id&quot;:

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

  El esquema generado:

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

### Clave principal: Identificador{#primary-key}

En el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), la clave principal de las tablas de Adobe Campaign es una **ID único universal (UUID)** generado automáticamente por el motor de base de datos. El valor clave es único en toda la base de datos. El contenido de la clave se genera automáticamente al insertar el registro.

**Por ejemplo**

Declarar una clave incremental en el esquema de origen:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

El esquema generado:

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

Además de la definición de la clave, se ha añadido un campo numérico llamado &quot;id&quot; al esquema ampliado para contener la clave principal generada automáticamente.

>[!CAUTION]
>
>Al crear la tabla, se inserta automáticamente un registro con una clave principal establecida en 0. Este registro se utiliza para evitar las uniones externas, que no son efectivas en las tablas de volumen. De forma predeterminada, todas las claves externas se inicializan con el valor 0, de modo que siempre se pueda devolver un resultado en la unión cuando el elemento de datos no se rellena.

## Vínculos: relación entre tablas {#links--relation-between-tables}

Un vínculo describe la asociación entre una tabla y otra.

Los distintos tipos de asociaciones (conocidas como &quot;cardinalidades&quot;) son los siguientes:

* Cardinality 1-1: una incidencia de la tabla de origen puede tener como máximo una incidencia correspondiente de la tabla de destino.
* Cardinality 1-N: una incidencia de la tabla de origen puede tener varias incidencias correspondientes de la tabla de destino, pero una incidencia de la tabla de destino puede tener como máximo una incidencia correspondiente de la tabla de origen.
* Cardinality N-N: una incidencia de la tabla de origen puede tener varias incidencias correspondientes de la tabla de destino y viceversa.

En la interfaz, puede distinguir los diferentes tipos de relaciones fácilmente gracias a sus iconos.

Para relaciones de unión con una tabla o base de datos de campaña:

* ![](assets/do-not-localize/join_with_campaign11.png) : Cardinalidad 1-1. Por ejemplo, entre un destinatario y un pedido actual. Un destinatario solo puede estar relacionado con una incidencia de la tabla de pedidos actual a la vez.
* ![](assets/do-not-localize/externaljoin11.png) : cardinalidad 1-1, unión externa. Por ejemplo, entre un destinatario y su país. Un destinatario solo puede estar relacionado con una incidencia del país de la tabla. No se guardará el contenido de la lista del país.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Cardinalidad 1-N. Por ejemplo, entre un destinatario y la tabla de suscripciones. Un destinatario puede estar relacionado con varias incidencias en la tabla de suscripciones.

Para relaciones de unión mediante el acceso a bases de datos federadas:

* ![](assets/do-not-localize/join_fda_11.png) : Cardinalidad 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : Cardinalidad 1-N

![](../assets/do-not-localize/glass.png) Para obtener más información sobre las tablas de FDA, consulte [Acceso de datos federado](../connect/fda.md).

Se debe declarar un vínculo en el esquema que contenga la clave externa de la tabla vinculada a través del elemento principal:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Los vínculos obedecen las siguientes reglas:

* La definición de un vínculo se introduce en una **vincular**-type **`<element>`** con los atributos siguientes:

   * **name**: nombre del vínculo de la tabla de origen,
   * **destino**: nombre del esquema de destino,
   * **etiqueta**: etiqueta del vínculo,
   * **revLink** (opcional): nombre del vínculo inverso desde el esquema de destino (deducido automáticamente de forma predeterminada),
   * **integridad** (opcional): integridad referencial de la incidencia de la tabla de origen a la incidencia de la tabla de destino. Los valores posibles son los siguientes:

      * **definir**: es posible eliminar la incidencia de origen si una incidencia de destino ya no hace referencia a ella,
      * **normal**: al eliminar la incidencia de origen se inicializan las claves del vínculo a la incidencia de destino (modo predeterminado), este tipo de integridad inicializa todas las claves externas,
      * **poseer**: si se elimina la incidencia de origen, se elimina la incidencia de destino,
      * **owncopy**: igual que **poseer** (en caso de eliminación) o duplica los sucesos (en caso de duplicación),
      * **neutral**: no hace nada.

   * **revIntegrity** (opcional): integridad en el esquema de destino (opcional, &quot;normal&quot; de forma predeterminada),
   * **revCardinality** (opcional): con el valor &quot;single&quot; rellena la cardinalidad con tipo 1-1 (1-N de forma predeterminada).
   * **externalJoin** (opcional): fuerza la unión externa
   * **revExternalJoin** (opcional): fuerza la unión externa en el vínculo inverso

* Un vínculo hace referencia a uno o varios campos de la tabla de origen a la tabla de destino. Los campos que componen la unión ( `<join>`  ) no es necesario rellenarlos porque se deducen automáticamente de forma predeterminada mediante la clave interna del esquema de destinatario.
* Un vínculo consta de dos semirvínculos, en los que el primero se declara desde el esquema de origen y el segundo se crea automáticamente en el esquema ampliado del esquema de destino.
* Una unión puede ser una unión externa si la variable **externalJoin** se agrega el atributo, con el valor &quot;true&quot; (admitido en PostgreSQL).

>[!NOTE]
>
>Los vínculos son los elementos declarados al final del esquema.

### Ejemplo 1 {#example-1}

Relación 1-N con la tabla de esquema &quot;cus:company&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

El esquema generado:

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

La definición del vínculo se complementa con los campos que conforman la unión, es decir, la clave principal con su XPath (&quot;@id&quot;) en el esquema de destino y la clave externa con su XPath (&quot;@company-id&quot;) en el esquema.

La clave externa se agrega automáticamente en un elemento que utiliza las mismas características que el campo asociado en la tabla de destino, con la siguiente convención de nombres: nombre del esquema de destino seguido del nombre del campo asociado (&quot;company-id&quot; en nuestro ejemplo).

Esquema extendido del destinatario (&quot;cus:company&quot;):

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

Se ha añadido un vínculo inverso a la tabla &quot;cus:recipient&quot; con los siguientes parámetros:

* **name**: se deduce automáticamente del nombre del esquema de origen (se puede forzar con el atributo &quot;revLink&quot; en la definición del vínculo en el esquema de origen)
* **revLink**: nombre del vínculo inverso
* **destino**: clave del esquema vinculado (esquema &quot;cus:recipient&quot;)
* **libre**: el vínculo se declara como elemento de colección para una cardinalidad 1-N (de forma predeterminada)
* **integridad**: &quot;definir&quot; de forma predeterminada (se puede forzar con el atributo &quot;revIntegrity&quot; en la definición del vínculo en el esquema de origen).

Tenga en cuenta que la variable `autouuid="true"`El parámetro se aplica en el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md) solo.

### Ejemplo 2 {#example-2}

En este ejemplo, declaramos un vínculo hacia la tabla de esquema &quot;nms:address&quot;. La unión es una unión externa y se rellena explícitamente con la dirección de correo electrónico del destinatario y el campo &quot;@address&quot; de la tabla vinculada (&quot;nms:address&quot;).

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

### Ejemplo 3 {#example-3}

Relación 1-1 con la tabla de esquema &quot;cus:extension&quot;:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Ejemplo 4 {#example-4}

Vínculo a una carpeta (esquema &quot;xtk:folder&quot;):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

El valor predeterminado devuelve el identificador del primer archivo de tipo de parámetro elegible introducido en la función &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;.

### Ejemplo 5 {#example-5}

En este ejemplo, deseamos crear una clave en un vínculo (&quot;empresa&quot; a &quot;cus:empresa&quot; esquema) con la variable **xlink** y un campo de la tabla (&quot;correo electrónico&quot;):

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

El esquema generado:

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

La definición de la clave del nombre &quot;companyEmail&quot; se amplió con la clave externa del vínculo &quot;company&quot;.
