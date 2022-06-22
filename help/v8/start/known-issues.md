---
title: Problemas conocidos de Campaign v8
description: Problemas conocidos en la última versión de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 0d1d20f9692ffa7b7ea7a8fb1161ebd19f533bab
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Problemas conocidos{#known-issues}

Esta página enumera los problemas conocidos identificados en el **última versión de Campaign v8**. Además, se enumeran las limitaciones que acompañan a Campaign v8 [en esta página](known-limitations.md).


>[!NOTE]
>
>Adobe publica esta lista de problemas conocidos a su propia discreción. Se basa en la cantidad de informes de clientes, la gravedad y la disponibilidad de la solución alternativa. Si un problema que encuentra no aparece en la lista, es posible que no se ajuste a los criterios de publicación de esta página.

## Cambio del problema de actividad de la fuente de datos n.º 1 {#issue-1}

### Descripción{#issue-1-desc}

La variable **Cambiar fuente de datos** la actividad de falla al transferir datos de la base de datos local de Campaign a la base de datos de nube de Snowflake. Al cambiar de dirección, la actividad puede generar problemas.

### Pasos de reproducción{#issue-1-repro}

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue un **Consulta** actividad y **Cambiar fuente de datos** actividad.
1. Defina una consulta en la variable **email**, que es una cadena.
1. Ejecute el flujo de trabajo y haga clic con el botón derecho en la transición para ver la población: los registros de correo electrónico se muestran reemplazados por `****`.
1. Compruebe los registros de flujo de trabajo: el **Cambiar fuente de datos** activity interpreta estos registros como valores numéricos.

### Mensaje de error{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Solución alternativa{#issue-1-workaround}

Para que los datos se transfieran de la base de datos de nube de Snowflake a la base de datos local de Campaign y se devuelvan al Snowflake, debe utilizar dos **Cambiar fuente de datos** actividades.

### Referencia interna{#issue-1-ref}

Referencia: NEO-45549



## Cambio del problema de actividad de la fuente de datos n.º 2 {#issue-2}

### Descripción{#issue-2-desc}

Al introducir datos en la base de datos de la nube de Snowflake con una campaña **Consulta** y **Cambiar fuente de datos** , el proceso falla cuando hay un carácter de barra invertida presente en los datos. La cadena de origen no se escapa y los datos no se procesan correctamente en el Snowflake.

Este problema solo ocurre si los caracteres de barra invertida se encuentran al final de la cadena, por ejemplo: `Barker\`.


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

Como solución alternativa, exporte los archivos con comillas dobles alrededor de los valores problemáticos (como `Barker\`) e incluir una opción de formato de archivo `FIELD_OPTIONALLY_ENCLOSED_BY = '"'`.

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

Debe utilizar una consola de cliente antigua para poder cargar el archivo en el servidor.

### Referencia interna{#issue-3-ref}

Referencia: NEO-47269