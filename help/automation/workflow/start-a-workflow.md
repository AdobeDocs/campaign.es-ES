---
product: campaign
title: Inicio de un flujo de trabajo
description: Obtenga información sobre cómo iniciar un flujo de trabajo y descubra acciones de flujos de trabajo en la barra de herramientas y el menú que aparece al hacer clic con el botón derecho
feature: Workflows
exl-id: 6d9789e3-d721-4ffd-b3fb-a0c522ab1c0a
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 97%

---

# Inicio de un flujo de trabajo {#starting-a-workflow}

Un flujo de trabajo siempre se inicia manualmente. Cuando se inicia, no obstante, puede permanecer inactivo según la información especificada mediante un planificador (consulte [Scheduler](scheduler.md)) o una planificación de actividad.

Las acciones relacionadas con la ejecución del flujo de trabajo de objetivos (inicio, detención, pausa, etc.) son procesos **asíncronos**: el comando se guarda y se aplica en cuanto el servidor esté disponible para su aplicación.

La barra de herramientas permite iniciar y rastrear la ejecución del flujo de trabajo.

A continuación se detalla la lista de opciones disponibles en el menú **[!UICONTROL Actions]** y el menú contextual.

>[!IMPORTANT]
>
>Tenga en cuenta que cuando un operador realiza una acción en un flujo de trabajo (inicio, detención, pausa, etc.), la acción no se ejecuta de inmediato, sino que se coloca en una cola para que la procese el módulo de flujo de trabajo.

## Barra de herramientas de acciones {#actions-toolbar}

El **[!UICONTROL Actions]** de la barra de herramientas permite acceder a opciones de ejecución adicionales en los flujos de trabajo seleccionados. También puede utilizar el menú **[!UICONTROL File > Actions]** o hacer clic con el botón derecho del ratón en un flujo de trabajo y seleccionar **[!UICONTROL Actions]**.

![](assets/purge_historique.png)

* **[!UICONTROL Start]**

  Esta acción le permite iniciar la ejecución de un flujo de trabajo: un flujo de trabajo que aparezca como **Finalizado**, **Edición en curso** o **En pausa** cambia de estado a **Iniciado**. El motor de flujo de trabajo gestiona entonces la ejecución de este flujo de trabajo. Si el flujo de trabajo estaba en pausa, se reanuda, pero de lo contrario el flujo de trabajo se inicia desde el principio y se activan las actividades iniciales.

  El inicio es un proceso asincrónico: la solicitud se guarda y se procesa lo antes posible mediante un servidor de flujo de trabajo.

* **[!UICONTROL Pause]**

  Esta acción establece el estado del flujo de trabajo como **En pausa**. No se activa ninguna actividad hasta que se reanuda el flujo de trabajo; sin embargo, las operaciones en curso no se detienen.

* **[!UICONTROL Stop]**

  Esta acción detiene un flujo de trabajo que se está ejecutando. El estado de la instancia se establece como **Finalizado**. Las operaciones en curso se detienen, si es posible. Las consultas SQL y las importaciones se cancelan inmediatamente.

  >[!IMPORTANT]
  >
  >La detención de un flujo de trabajo es un proceso asíncrono: la solicitud se registra y, después, el servidor o los servidores de flujo de trabajo cancelan las operaciones en curso. Por lo tanto, la detención de una instancia de flujo de trabajo puede llevar tiempo, especialmente si el flujo de trabajo se ejecuta en varios servidores, cada uno de los cuales debe asumir el control para cancelar las tareas en curso. Para evitar cualquier problema, espere a que se complete la operación de detención y no realice varias solicitudes en el mismo flujo de trabajo.

* **[!UICONTROL Restart]**

  Esta acción detiene y reinicia el flujo de trabajo. En la mayoría de los casos, es posible reiniciarlo más rápido. También resulta útil automatizar el reinicio cuando la detención lleva una determinada cantidad de tiempo: esto sucede porque el comando “Detener” no está disponible cuando el flujo de trabajo se detiene.

* **[!UICONTROL Purge history]**

  Esta acción permite depurar el historial del flujo de trabajo. Para obtener más información, consulte [Depuración de “logs”](monitor-workflow-execution.md#purging-the-logs).

* **[!UICONTROL Start in simulation mode]**

  Esta opción permite iniciar el flujo de trabajo en modo de simulación, distinto del modo real. Esto significa que, cuando se activa este modo, solo se ejecutan las actividades que no afectan a la base de datos o al sistema de archivos (por ejemplo **[!UICONTROL Query]**, **[!UICONTROL Union]**, **[!UICONTROL Intersection]**, etc.). Actividades que sí tienen impacto (por ejemplo, **[!UICONTROL Export]**, **[!UICONTROL Import]**, etc.). no se ejecutan ni los que se encuentran después de ellos (en la misma rama).

* **[!UICONTROL Execute pending tasks now]**

  Esta acción le permite iniciar todas las tareas pendientes lo antes posible. Para iniciar una tarea específica, haga clic con el botón derecho en su actividad y seleccione **[!UICONTROL Execute pending task(s) now]**.

* **[!UICONTROL Unconditional stop]**

  Esta opción cambia el estado del flujo de trabajo a **[!UICONTROL Finished]**. Esta acción debe utilizarse únicamente como último recurso si el proceso de detención normal falla tras varios minutos. Utilice únicamente la detención incondicional si está seguro de que no hay tareas de trabajos de flujo en curso.

  >[!CAUTION]
  >
  >Esta opción se reserva para usuarios expertos.

* **[!UICONTROL Save as template]**

  Esta acción crea una nueva plantilla de flujo de trabajo basada en el flujo de trabajo seleccionado. Debe especificar la carpeta donde desea que se guarde (en el campo **[!UICONTROL Folder]**).

## Menú del botón derecho {#right-click-menu}

Cuando haya seleccionado una o más actividades de flujo de trabajo, puede hacer clic con el botón derecho para actuar sobre la selección.

![](assets/contextual_menu.png)

Las siguientes opciones están disponibles en el menú del botón derecho:

**[!UICONTROL Open]**: esta opción permite acceder a las propiedades de la actividad.

**[!UICONTROL Display logs:]** esta opción permite ver el “log” de ejecución de la tarea para la actividad seleccionada. Consulte [Visualización de “logs”](monitor-workflow-execution.md#displaying-logs).

**[!UICONTROL Execute pending task(s) now:]** esta acción permite iniciar tareas pendientes lo antes posible.

**[!UICONTROL Workflow restart from a task:]** esta opción permite reiniciar el flujo de trabajo con los resultados almacenados anteriormente para esta actividad.

**[!UICONTROL Cut/Copy/Paste/Delete:]** estas opciones permiten cortar, copiar, pegar y eliminar actividades.

**[!UICONTROL Copy as bitmap:]** esta opción permite realizar una captura de pantalla de todas las actividades.

**[!UICONTROL Normal execution / Enable but do not execute / Do not enable:]** : estas opciones están disponibles en la pestaña **[!UICONTROL Advanced]** de las propiedades de actividad. Se encuentran detalladas en [Execution](advanced-parameters.md#execution).

**[!UICONTROL Save / Cancel:]** permite guardar o cancelar los cambios realizados en un flujo de trabajo.

>[!NOTE]
>
>Puede seleccionar un grupo de actividades y aplicar uno de estos comandos.

