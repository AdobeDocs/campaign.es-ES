---
solution: Campaign
product: Adobe Campaign
title: Trabajo con esquemas de Campaign
description: Introducción a los esquemas
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 7%

---

# Trabajar con esquemas{#gs-ac-schemas}

La estructura física y lógica de los datos que se llevan en la aplicación se describe en XML. Obedece a una gramática específica de Adobe Campaign, denominada **schema**.

Un esquema es un documento XML asociado a una tabla de base de datos. Define la estructura de datos y describe la definición SQL de la tabla:

* Nombre de la tabla
* Campos
* Vínculos con otras tablas

También describe la estructura XML utilizada para almacenar datos:

* Elementos y atributos
* Jerarquía de elementos
* Tipos de elementos y atributos
* Valores predeterminados
* Etiquetas, descripciones y otras propiedades.

Los esquemas permiten definir una entidad en la base de datos. Hay un esquema para cada entidad.

Adobe Campaign emplea esquemas de datos para:

* Defina cómo los objetos de datos de la aplicación están vinculados a las tablas de base de datos subyacentes.
* Definir vínculos entre los diferentes objetos de datos dentro de la aplicación de Campaign.
* Definir y describir los campos individuales incluidos en cada objeto.

Para comprender mejor las tablas integradas de Campaign y su interacción, consulte [esta sección](datamodel.md).

>[!CAUTION]
>
>Algunos esquemas de Campaign integrados tienen un esquema asociado en la base de datos de Cloud. Estos esquemas están identificados por el espacio de nombres **Xxl** y no deben modificarse.

## Sintaxis de esquemas {#syntax-of-schemas}

El elemento raíz del esquema es **`<srcschema>`**. Contiene los subelementos **`<element>`** y **`<attribute>`**.

El primer subelemento **`<element>`** coincide con la raíz de la entidad.

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
>El elemento raíz de la entidad tiene el mismo nombre que el esquema.

![](assets/schema_and_entity.png)

Las etiquetas **`<element>`** definen los nombres de los elementos de entidad. **`<attribute>`** las etiquetas del esquema definen los nombres de los atributos en las  **`<element>`** etiquetas a las que se han vinculado.

## Identificación de un esquema {#identification-of-a-schema}

Un esquema de datos se identifica con su nombre y área de nombres.

Un área de nombres permite agrupar un conjunto de esquemas por área de interés. Por ejemplo, el espacio de nombres **cus** se utiliza para la configuración específica del cliente (**customers**).

>[!CAUTION]
>
>Como estándar, el nombre del área de nombres debe ser conciso y contener únicamente caracteres autorizados de acuerdo con las reglas de nomenclatura XML.
>
>Los identificadores no deben comenzar con caracteres numéricos.

## Espacios de nombres reservados

Algunas áreas de nombres están reservadas para descripciones de las entidades del sistema necesarias para el funcionamiento de la aplicación Adobe Campaign. El siguiente espacio de nombres **no debe utilizarse** para identificar un nuevo esquema, en cualquier combinación de mayúsculas y minúsculas:

* **xxl**: reservado a esquemas de base de datos de Cloud,
* **xtk**: reservado para datos del sistema de plataforma,
* **nl**: reservado para el uso general de la aplicación,
* **nms**: reservado para entregas (destinatario, entrega, seguimiento, etc.),
* **ncm**: reservado para la gestión de contenido,
* **temp**: reservado para esquemas temporales.

La clave de identificación de un esquema es una cadena creada con el área de nombres y el nombre separado por dos puntos; por ejemplo: **nms:recipient**.

## Crear o ampliar esquemas de Campaign {#create-or-extend-schemas}

Para añadir un campo u otro elemento a uno de los esquemas de datos principales de Campaign, como la tabla de destinatarios (nms:recipient), debe ampliar ese esquema.

:bulb: Para obtener más información, consulte [Ampliar un esquema](extend-schema.md).

Para añadir un tipo de datos completamente nuevo que no exista en Adobe Campaign (por ejemplo, una tabla de contratos), puede crear un esquema personalizado directamente.

:bulb: Para obtener más información, consulte [Crear un nuevo esquema](create-schema.md).

![](assets/schemaextension_1.png)


Una vez que haya creado o ampliado un esquema para que funcione, la práctica recomendada es definir sus elementos de contenido XML en el mismo orden en que aparecen a continuación.

## Enumeraciones {#enumerations}

Las enumeraciones se definen primero, antes del elemento principal del esquema. Permiten mostrar valores en una lista para restringir las opciones que el usuario tiene para un campo determinado.

Ejemplo:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Al definir campos, puede utilizar esta enumeración de la siguiente manera:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>También puede utilizar enumeraciones administradas por el usuario (normalmente en **[!UICONTROL Administration]** > **[!UICONTROL Platform]** ) para especificar los valores de un campo determinado. Se trata de enumeraciones globales eficaces y una mejor opción si la enumeración puede utilizarse fuera del esquema específico en el que está trabajando.

## Claves {#keys}

Cada tabla debe tener al menos una clave y, a menudo, se establece automáticamente en el elemento principal del esquema mediante el atributo **@autouuid=true** establecido en &quot;true&quot;.

La clave principal también se puede definir utilizando el atributo **internal**.

Ejemplo:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

En este ejemplo, en lugar de permitir que el atributo **@autouuid** cree una clave principal predeterminada denominada &quot;id&quot;, especificamos nuestra propia clave principal &quot;householdId&quot;.

>[!CAUTION]
>
>Al crear un nuevo esquema o durante una ampliación de esquema, se debe mantener el mismo valor de secuencia de clave principal (@pkSequence) para todo el conjunto.

:bulb: Obtenga más información sobre las claves en [esta sección](database-mapping.md#management-of-keys).

## Atributos (campos) {#attributes--fields-}

Los atributos permiten definir los campos que conforman el objeto de datos. Puede utilizar el botón **[!UICONTROL Insert]** de la barra de herramientas de edición de esquema para soltar plantillas de atributos vacías en el XML donde se encuentra el cursor. Obtenga más información en [esta sección](create-schema.md).

![](assets/schemaextension_2.png)

La lista completa de atributos está disponible en la sección `<attribute>` del elemento de la sección [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Estos son algunos de los atributos más utilizados: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **@label a13/>,**@length **,**@name **,**@notNull **,**@required **,**@ref **3/>,**@xml **,**@type **.**

:arrow_upper_right: Para obtener más información sobre cada atributo, consulte la descripción del atributo en [documentación del Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Ejemplos {#examples}

Ejemplo de definición de un valor predeterminado:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Ejemplo de uso de un atributo común como plantilla para un campo también marcado como obligatorio:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Ejemplo de un campo calculado que está oculto con el atributo **@advanced** :

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Ejemplo de un campo XML también almacenado en un campo SQL y que tiene un atributo **@dataPolicy**.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Aunque la mayoría de los atributos están vinculados según una cardinalidad 1-1 a un campo físico de la base de datos, este no es el caso de los campos XML o los campos calculados.\
>Un campo XML se almacena en un campo memo (&quot;mData&quot;) de la tabla.\
>Sin embargo, un campo calculado se crea dinámicamente cada vez que se inicia una consulta, por lo que solo existe en la capa aplicativa.

## Vínculos {#links}

Los vínculos son algunos de los últimos elementos del elemento principal del esquema. Definen cómo se relacionan todos los distintos esquemas de la instancia entre sí.

Los vínculos se declaran en el esquema que contiene la **clave externa** de la tabla a la que están vinculados.

Hay tres tipos de cardinalidad: 1-1, 1-N y N-N. Es el tipo 1-N que se utiliza de forma predeterminada.

### Ejemplos {#examples-1}

Ejemplo de un vínculo 1-N entre la tabla de destinatarios (esquema predeterminado) y una tabla de transacciones personalizadas:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Ejemplo de un vínculo 1-1 entre un esquema personalizado &quot;Car&quot; (en el espacio de nombres &quot;cus&quot;) y la tabla de destinatarios:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Ejemplo de un vínculo externo entre la tabla de destinatarios y una tabla de direcciones basada en la dirección de correo electrónico y no en una clave principal:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Aquí &quot;xpath-dst&quot; corresponde a la clave principal en el esquema de destino y &quot;xpath-src&quot; corresponde a la clave externa en el esquema de origen.

## Pista de auditoría {#audit-trail}

Un elemento útil que puede querer incluir en la parte inferior del esquema es un elemento de seguimiento (pista de auditoría).

Utilice el ejemplo siguiente para incluir campos relacionados con la fecha de creación, el usuario que creó los datos, la fecha y el autor de la última modificación para todos los datos de la tabla:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Actualización de la estructura de la base de datos {#updating-the-database-structure}

Una vez completados y guardados los cambios, cualquier cambio que pueda afectar a la estructura SQL debe aplicarse a la base de datos. Para ello, utilice el asistente de actualización de la base de datos.

![](assets/schemaextension_3.png)

Para obtener más información, consulte [esta sección](update-database-structure.md).

>[!NOTE]
>
>Cuando las modificaciones no afectan a la estructura de la base de datos, solo es necesario volver a generar los esquemas. Para ello, seleccione los esquemas que desea actualizar, haga clic con el botón derecho y elija **[!UICONTROL Actions > Regenerate selected schemas...]** .

