---
product: campaign
title: Administración de zonas horarias
description: Administración de zonas horarias
feature: Workflows, Configuration
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
TQID: https://experienceleague.adobe.com/M8aAiSm2KJdcKX0VuqX4NCIecbOm6u6B7xCvgs4bW-c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 100%

---

# Administración de zonas horarias{#managing-time-zones}

Adobe Campaign le permite administrar desfases temporales entre los distintos países de la misma instancia. La configuración aplicada se configura durante la creación de instancias.

En un flujo de trabajo, puede adaptar las programaciones de ejecución de una actividad y vincular una zona horaria específica a una actividad o a todo el flujo de trabajo. Esta configuración puede resultar útil al importar el archivo o en el contexto de la programación de envíos.

## Programación de la ejecución {#execution-scheduling}

Puede planificar la ejecución de tareas utilizando el planificador (consulte [Planificador](scheduler.md)). También puede utilizar las opciones de planificación disponibles en las actividades que ofrecen esta funcionalidad. Estas actividades ofrecen una pestaña **[!UICONTROL Schedule]**: **[!UICONTROL File collector]**, **[!UICONTROL File transfer]**, **[!UICONTROL Web download]**, **[!UICONTROL Email reception]** y **[!UICONTROL SMS]**, etc.

Para todas las tareas planificadas, es decir, todas las actividades con opciones de planificación, puede seleccionar la zona horaria que desee aplicar. La zona horaria se selecciona a través de la pestaña **[!UICONTROL Advanced]** de la actividad correspondiente:

![](assets/wf-timezone-in-a-box.png)

Los valores posibles son:

* Zona horaria del servidor

  Utiliza la zona horaria del servidor de aplicaciones de Adobe Campaign.

* Zona horaria del usuario

  Utiliza la zona horaria del operador de Adobe Campaign que ejecuta el flujo de trabajo.

* Zona horaria de la base de datos

  Utiliza la zona horaria del servidor de la base de datos utilizado.

* Zonas horarias específicas

  Utiliza la zona horaria seleccionada.

Si se selecciona el valor **[!UICONTROL By default]**, se aplica la zona horaria del flujo de trabajo o, en caso contrario, la del servidor de aplicaciones.

## Vinculación de una zona horaria a una actividad {#linking-a-time-zone-to-an-activity}

La pestaña **[!UICONTROL Advanced]** de las actividades de flujo de trabajo permite seleccionar su zona horaria. Aunque la mayor parte del tiempo la zona horaria del flujo de trabajo es suficiente, puede ser necesario sobrecargarla de vez en cuando para una actividad específica, como la importación de datos, para vincular las fechas a la zona horaria correcta.
