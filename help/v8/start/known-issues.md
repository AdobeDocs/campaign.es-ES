---
title: Problemas conocidos de Campaign v8
description: Problemas conocidos en la última versión de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Problemas conocidos{#known-issues}

Esta página enumera los problemas conocidos identificados en el **última versión de Campaign v8**. Además, se enumeran las limitaciones que acompañan a Campaign v8 [en esta página](known-limitations.md).


>[!NOTE]
>
>Adobe publica esta lista de problemas conocidos a su propia discreción. Se basa en la cantidad de informes de clientes, la gravedad y la disponibilidad de la solución alternativa. Si un problema que encuentra no aparece en la lista, es posible que no se ajuste a los criterios de publicación de esta página.

## Cambiar el problema de la actividad de la fuente de datos {#issue-1}

### Descripción

La variable **Cambiar fuente de datos** la actividad de falla al transferir datos de la base de datos local de Campaign a la base de datos de nube de Snowflake. Al cambiar de dirección, la actividad puede generar problemas.

### Pasos de reproducción

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue un **Consulta** actividad y **Cambiar fuente de datos** actividad.
1. Defina una consulta en la variable **email**, que es una cadena.
1. Ejecute el flujo de trabajo y haga clic con el botón derecho en la transición para ver la población: los registros de correo electrónico se muestran reemplazados por `****`.
1. Compruebe los registros de flujo de trabajo: el **Cambiar fuente de datos** activity interpreta estos registros como valores numéricos.

### Solución alternativa

Para que los datos se transfieran de la base de datos de nube de Snowflake a la base de datos local de Campaign y se devuelvan al Snowflake, debe utilizar dos **Cambiar fuente de datos** actividades.

### Referencia interna

Referencia: NEO-45549


## La actividad de carga de datos (archivos) no pudo Cargar archivo en el servidor {#issue-2}

### Descripción

La carga de archivos en el servidor de Campaign se detiene al 100% de progreso, pero nunca termina.

### Pasos de reproducción

1. Conéctese a la consola del cliente y cree un flujo de trabajo.
1. Agregue un **Carga de datos (archivos)** y configúrela.
1. Seleccione el **Cargar en el servidor** .
1. Seleccione el archivo en el equipo local,
1. Haga clic en **Cargar**

### Solución alternativa

Ninguno

### Referencia interna

Referencia: NEO-47269