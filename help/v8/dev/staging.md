---
solution: Campaign v8
product: Adobe Campaign
title: Mecanismo de ensayo de la API de Campaign
description: Mecanismo de ensayo de la API de Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 3%

---

# Mecanismo de ensayo de la API de Campaign

Con la base de datos de Campaign Cloud, no se recomiendan las llamadas unitarias blast debido al rendimiento (latencia y concurrencia). Siempre se prefiere el funcionamiento por lotes. Para garantizar un rendimiento óptimo de las API, Campaign sigue gestionando las llamadas de API a nivel de base de datos local.

El mecanismo de ensayo de campañas está disponible para tablas integradas y personalizadas, y ofrece las siguientes ventajas:

* La estructura del esquema de datos se duplica en la tabla de ensayo local
* Las nuevas API para la ingesta fluyen directamente a la tabla de ensayo. [Obtenga más información](new-apis.md)
* Un flujo de trabajo programado déclencheur cada hora y sincroniza los datos con la base de datos de Cloud. [Más información](../config/replication.md).

Algunos esquemas integrados están Ensayados de forma predeterminada, como nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Las API de Campaign Classic v7 siguen disponibles, pero no pueden beneficiarse de este nuevo mecanismo de ensayo: Las llamadas a API fluyen directamente a la base de datos de Cloud. Adobe recomienda utilizar el nuevo mecanismo de ensayo en la medida de lo posible para reducir la presión general y la latencia en la base de datos de Campaign Cloud.

>[!CAUTION]
>
>Con este nuevo mecanismo, la sincronización de datos para suscripciones, bajas de suscripción o registro móvil es ahora **asíncrona**.


## Pasos de implementación{#implement-staging}

Para implementar el mecanismo de ensayo de Campaign en una tabla específica, siga los pasos a continuación:

1. Cree un esquema personalizado de ejemplo en la base de datos de Campaign Cloud. No se ha habilitado el ensayo en este paso.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   :bulb: Obtenga más información sobre la creación de esquemas personalizados en [esta página](create-schema.md).

1. Guarde y actualice la estructura de la base de datos.  [Obtenga más información](update-database-structure.md)

1. Habilite el mecanismo de ensayo en la definición del esquema añadiendo el parámetro **autoStg=&quot;true&quot;**.

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. Guarde la modificación. Hay disponible un nuevo esquema de ensayo, que es una copia local del esquema inicial.

   ![](assets/staging-mechanism.png)

1. Actualice la estructura de la base de datos. La tabla de ensayo se creará en la base de datos local de Campaign.
