---
product: campaign
title: Parámetros avanzados
description: Parámetros avanzados
feature: Workflows, Data Management
exl-id: aafd977e-c8af-426b-904c-8388c9d8e595
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 100%

---

# Parámetros avanzados{#advanced-parameters}



La pantalla de propiedades de una actividad tiene una pestaña **[!UICONTROL Advanced]** que permite definir un comportamiento en caso de errores, establecer el periodo de ejecución de la actividad e introducir una secuencia de comandos de inicialización. Existen dos versiones de esta pestaña:

* una versión simplificada (para las actividades **[!UICONTROL Start]** y **[!UICONTROL End]**, por ejemplo)

  ![](assets/wf-advanced-basic.png)

* una versión más detallada (para la actividad **[!UICONTROL Query]**, por ejemplo)

  ![](assets/wf-advanced-full.png)

Los campos que se introducen en la pestaña **[!UICONTROL Advanced]** se describen en las siguientes secciones.

## Nombre {#name}

Este campo contiene el nombre interno de la actividad.

## Imagen {#image}

Este campo permite cambiar la imagen vinculada a una actividad. Para obtener más información sobre esto, consulte [Cambio de imágenes de actividad](change-activity-images.md).

## Ejecución {#execution}

Este campo permite definir la acción que se ejecuta al activarse la tarea. Hay tres opciones posibles:

Generalmente, estas opciones se seleccionan en el carro haciendo clic con el botón derecho sobre la actividad.

* **[!UICONTROL Normal]**: la actividad se ejecuta de la forma habitual.
* **[!UICONTROL Do not activate]**: esta tarea y todas las tareas siguientes (en la misma rama) no se ejecutan.
* **[!UICONTROL Activate but do not execute]**: esta tarea y todas las tareas siguientes (en la misma rama) se detienen automáticamente. Esto puede resultar útil si desea estar presente cuando comience la tarea. Para ejecutar la tarea manualmente, haga clic con el botón derecho en la actividad y seleccione **[!UICONTROL Normal execution]**.

## Afinidad {#affinity}

Puede optar por forzar la ejecución de un flujo de trabajo o actividad de flujo de trabajo en un equipo concreto. Para ello, debe definir una o más tendencias al nivel del flujo de trabajo o la actividad pertinente.


## Máx. periodo de ejecución {#max--execution-period}

Este campo permite establecer una advertencia para los casos en los que la tarea tarde demasiado. No afecta a la operación del flujo de trabajo. Si la tarea no ha finalizado en el momento en que haya terminado el **[!UICONTROL Max. execution period]**, la página **[!UICONTROL Instance monitoring]** muestra una advertencia para este flujo de trabajo. Se accede a esta página a través de la pestaña **[!UICONTROL Monitoring]** de la página principal.

## Comportamiento {#behavior}

Este campo permite definir el comportamiento que se debe aplicar al utilizar tareas asíncronas. Hay dos opciones posibles:

* **[!UICONTROL Several tasks authorized]**: se pueden ejecutar varias tareas a la vez, incluso si no ha finalizado la primera.
* **[!UICONTROL The current task has priority]**: las tareas en curso tienen prioridad. Mientras una tarea esté en curso, no se ejecuta ninguna otra tarea.

## Zona horaria {#time-zone}

Este campo permite seleccionar la zona horaria de la actividad. Para más información sobre esto: [Administración de zonas horarias](managing-time-zones.md).

## En caso de errores {#in-case-of-errors}

Este campo permite definir la acción que debe llevarse a cabo cuando la actividad presenta errores. Hay dos opciones posibles:

* **[!UICONTROL Suspend the process]**: el flujo de trabajo se detiene automáticamente. Su estado cambia a **[!UICONTROL Failed]**. Una vez resuelto el problema, reinicie el flujo de trabajo.
* **[!UICONTROL Ignore]**: esta tarea y todas las tareas siguientes (en la misma rama) no se ejecutan. Esto puede resultar útil para tareas recurrentes. Si la rama tiene un planificador en una posición anterior, este se ejecuta con normalidad en la siguiente fecha de ejecución.
* **[!UICONTROL Abort on error]**: el flujo de trabajo se detiene automáticamente y no se puede reiniciar. Su estado cambia a **[!UICONTROL Failed]**.

## Secuencia de comandos de inicialización {#initialization-script}

Este campo permite inicializar las variables o modificar las propiedades de la actividad. Para obtener más información, consulte [Scripts y plantillas de JavaScript](javascript-scripts-and-templates.md).

## Comentario {#comment}

El campo **[!UICONTROL Comment]** es un campo libre que permite añadir una descripción.
