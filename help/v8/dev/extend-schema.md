---
solution: Campaign Classic
product: campaign
title: Ampliación de esquemas de Campaign
description: Descubra cómo ampliar los esquemas de Campaign
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---

# Ampliar un esquema{#extend-schemas}

En este artículo se describe cómo configurar esquemas de extensión para ampliar el modelo de datos conceptuales de la base de datos de Adobe Campaign.

:bulb: Para comprender mejor las tablas integradas de Campaign y su interacción, consulte [esta página](datamodel.md).

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

Algunas áreas de nombres están reservadas para descripciones de las entidades del sistema necesarias para el funcionamiento de la aplicación Adobe Campaign:

* **xxl**: sobre esquemas de base de datos de Cloud,
* **xtk**: sobre los datos del sistema de plataforma,
* **nl**: sobre el uso global de la solicitud,
* **nms**: sobre la entrega (destinatario, entrega, seguimiento, etc.),
* **ncm**: sobre la gestión de contenido,
* **temp**: reservado para esquemas temporales.

La clave de identificación de un esquema es una cadena creada con el área de nombres y el nombre separado por dos puntos; por ejemplo: **nms:recipient**.
