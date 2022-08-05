---
title: Problemas conocidos de Campaign v8
description: Problemas conocidos en la última versión de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 3d84bb9493251afa7b7e89a07469d299ff412c24
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 3%

---

# Problemas conocidos{#known-issues}

Esta página enumera los problemas conocidos identificados en el **última versión de Campaign v8**. Además, se enumeran las limitaciones que acompañan a Campaign v8 [en esta página](ac-guardrails.md).


>[!NOTE]
>
>Adobe publica esta lista de problemas conocidos a su propia discreción. Se basa en la cantidad de informes de clientes, la gravedad y la disponibilidad de la solución alternativa. Si un problema que encuentra no aparece en la lista, es posible que no se ajuste a los criterios de publicación de esta página.

<!--
## Change Data Source activity issue #1 {#issue-1}

### Description{#issue-1-desc}

The **Change Data Source** activity is failing when transfering data from Campaign local database to Snowflake cloud database. When switching directions, the activity can generate issues.

### Reproduction steps{#issue-1-repro}

1. Connect to the client console and create a workflow.
1. Add a **Query** activity and a **Change Data Source** activity.
1. Define a query on the **email**, which is a string.
1. Run the workflow and right-click the transition to view the population: the email records are displayed replaced by `****`.
1. Check the workflow logs: the **Change Data Source** activity interprets these records as numeric values.

### Error message{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Workaround{#issue-1-workaround}

To have the data transfered from Snowflake cloud database to Campaign local database and back to Snowflake, you must use two different **Change Data Source** activities.

### Internal reference{#issue-1-ref}

Reference: NEO-45549 
-->


## Cambiar el problema de la actividad de la fuente de datos {#issue-2}

### Descripción{#issue-2-desc}

Al introducir datos en la base de datos de la nube de Snowflake con una campaña **Consulta** y **Cambiar fuente de datos** , el proceso falla cuando hay un carácter de barra invertida presente en los datos. La cadena de origen no se escapa y los datos no se procesan correctamente en el Snowflake.

Este problema solo ocurre si el carácter de barra invertida se encuentra al final de la cadena, por ejemplo: `Barker\`.


### Pasos de reproducción{#issue-2-repro}

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue un **Consulta** y configúrela.
1. Seleccionar datos con las características descritas anteriormente.
1. Agregue un **Cambiar fuente de datos** y configúrela para seleccionar la base de datos de nube de Snowflake.
1. Ejecute el flujo de trabajo y compruebe los registros del flujo de trabajo para ver el error.


### Mensaje de error{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Solución alternativa{#issue-2-workaround}

La solución consiste en excluir los datos que contienen caracteres de barra invertida al final de la cadena o eliminarlos del archivo de origen.

<!--
As a workaround, export the files with double quotes around the problematic values (like `Barker\`) and include a file format option `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.
-->

### Referencia interna{#issue-2-ref}

Referencia: NEO-45549


## La actividad de carga de datos (archivos) no pudo Cargar archivo en el servidor {#issue-3}

### Descripción{#issue-3-desc}

Al cargar un archivo en el servidor de Campaign con un **Carga de datos (archivos)** actividad, el proceso se detiene al 100 % pero nunca finaliza.

### Pasos de reproducción{#issue-3-repro}

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue un **Carga de datos (archivos)** y configúrela.
1. Seleccione el **Cargar en el servidor** .
1. Seleccione el archivo en el equipo local,
1. Haga clic en **Cargar**


### Mensaje de error{#issue-3-error}

El proceso nunca termina.

### Solución alternativa{#issue-3-workaround}

La solución es utilizar una consola de cliente más antigua. A continuación, podrá cargar el archivo en el servidor.

Como administrador de Campaign, puede descargar la consola del cliente de Campaign v8.3.1 en [Distribución del software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Campaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Obtenga información sobre cómo acceder a la distribución de software de Adobe [en esta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=es){target=&quot;_blank&quot;}.

Obtenga información sobre cómo actualizar la consola del cliente [en esta página](connect.md)

### Referencia interna{#issue-3-ref}

Referencia: NEO-47269
