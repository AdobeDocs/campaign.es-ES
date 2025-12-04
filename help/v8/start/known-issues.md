---
title: Problemas conocidos de Campaign v8
description: Problemas conocidos en la última versión de Campaign
feature: Overview
role: Developer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# Problemas conocidos{#known-issues}

Esta página lista los problemas conocidos identificados en las **últimas versiones de Campaign v8**. Además, las limitaciones que vienen con Campaign v8 se enumeran [en esta página](ac-guardrails.md).


>[!NOTE]
>
>Adobe publica esta lista de problemas conocidos según su criterio. Se basa en el número de informes de clientes, la gravedad y la disponibilidad de la solución. Si un problema que encuentra no aparece en la lista, es posible que no cumpla los criterios de publicación de esta página.

## Campaign v8.3.8{#8.3-issues}

### Cambiar problema de actividad de Data Source {#issue-2}

#### Descripción{#issue-2-desc}

Al insertar datos en la base de datos de nube de Snowflake con una actividad de **Query** de Campaign y **Change Data Source**, el proceso falla cuando hay un carácter de barra invertida en los datos. La cadena de origen no se escapa y los datos no se procesan correctamente en Snowflake.

Este problema solamente ocurre si el carácter de barra invertida está al final de la cadena, por ejemplo: `Barker\`.


#### Pasos de reproducción{#issue-2-repro}

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue una actividad **Query** y configúrela.
1. Seleccione datos con las características descritas anteriormente.
1. Agregue una actividad **Cambiar datos de Source** y configúrela para seleccionar la base de datos en la nube de Snowflake.
1. Ejecute el flujo de trabajo y compruebe los registros de flujo de trabajo para ver el error.


#### Mensaje de error{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Solución alternativa{#issue-2-workaround}

La solución consiste en excluir los datos que contienen caracteres de barra invertida al final de la cadena o eliminarlos del archivo de origen.


#### Referencia interna{#issue-2-ref}

Referencia: NEO-45549


### La actividad Data loading (file) no se pudo cargar el archivo en el servidor {#issue-3}

#### Descripción{#issue-3-desc}

Al cargar un archivo en el servidor de Campaign con una actividad **Data loading (file)** , el proceso se detiene al 100 % pero nunca termina.

#### Pasos de reproducción{#issue-3-repro}

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue una actividad **Carga de datos (archivo)** y configúrela.
1. Seleccione la opción **Cargar en el servidor**.
1. Seleccione el archivo en el equipo local,
1. Haga clic en **Cargar**


#### Mensaje de error{#issue-3-error}

El proceso nunca termina.

#### Solución alternativa{#issue-3-workaround}

La solución consiste en utilizar una consola de cliente anterior. A continuación, podrá cargar el archivo en el servidor.

Como administrador de Campaign, puede descargar la consola de cliente versión 8.3.1 de Campaign en [Distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&1_group.propertyvalues.operation=equals&1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&orderby.sort=desc&layout=list&p.offset=0&p.limit=4){target="_blank"}.

Obtenga información sobre cómo obtener acceso a la distribución de software de Adobe [en esta página](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=es){target="_blank"}.

Obtenga información sobre cómo actualizar la consola de cliente [en esta página](connect.md)

#### Referencia interna{#issue-3-ref}

Referencia: NEO-47269

