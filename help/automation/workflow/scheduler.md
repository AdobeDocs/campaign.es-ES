---
product: campaign
title: Planificador
description: Descubra más información sobre la actividad del flujo de trabajo Planificador
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 42%

---

# Planificador {#scheduler}



El **Scheduler** es una tarea persistente que activa su transición en el momento especificado por su programación.

La actividad del **[!UICONTROL Scheduler]** debe considerarse como un inicio programado. Las reglas de colocación de actividad dentro del gráfico son las mismas que para la actividad **[!UICONTROL Start]**. Esta actividad no debe tener una transición entrante.

## Prácticas recomendadas {#best-practices}

**Reinicie el flujo de trabajo después de cambiar el horario del programador** - Al cambiar el horario programado de la actividad **[!UICONTROL Scheduler]**, es importante reiniciar el flujo de trabajo. Esto garantiza que el flujo de trabajo se ejecute en los momentos actualizados. Sin reiniciarlo, el flujo de trabajo seguirá ejecutándose según la programación antigua.

**Limitar la frecuencia del programador**: evite programar flujos de trabajo para que se ejecuten con una frecuencia superior a 15 minutos. Ejecutarlos con mayor frecuencia puede degradar el rendimiento del sistema y provocar una congestión de la base de datos.

**Use un Planificador por rama**: cada rama del flujo de trabajo solo debe tener una actividad **[!UICONTROL Scheduler]**. Para obtener más información sobre las prácticas recomendadas para usar actividades en flujos de trabajo, consulte la [página de prácticas recomendadas de flujo de trabajo](workflow-best-practices.md#using-activities).

**Impedir ejecuciones simultáneas en un flujo de trabajo**: si un programador activa un flujo de trabajo, tenga en cuenta que se podrían ejecutar varias instancias del flujo de trabajo al mismo tiempo. Por ejemplo, si un planificador procesa el flujo de trabajo cada hora, pero éste tarda más de una hora, podría terminar con déclencheur superpuestos. Para evitarlo, plantéese configurar comprobaciones para evitar varias ejecuciones simultáneas. [Aprenda a evitar ejecuciones simultáneas de varios flujos de trabajo](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

**Cuenta para transiciones retrasadas**: las transiciones activadas por el programador pueden retrasarse si el flujo de trabajo ejecuta tareas de larga ejecución (como importaciones) o si el módulo wfserver se ha detenido temporalmente. Para mitigar esto, restrinja los tiempos de activación del planificador para garantizar que las tareas se ejecuten dentro de un intervalo de tiempo definido.

## Configuración de la actividad Planificador {#configuring-scheduler-activity}

El planificador define la programación de activación de la transición. Para configurarlo, haga doble clic en el objeto gráfico y, a continuación, haga clic en **[!UICONTROL Change...]**.

![](assets/s_user_segmentation_scheduler.png)

Un asistente le permite definir la frecuencia y el periodo de validez de la actividad. Los pasos de configuración son los siguientes:

1. Seleccione la frecuencia de activación y haga clic en **[!UICONTROL Next]**.

   ![](assets/s_user_segmentation_scheduler2.png)

1. Indique las horas y días de activación. Los parámetros de este paso dependen de la frecuencia seleccionada en el paso anterior. Si elige iniciar la actividad varias veces al día, las opciones de configuración serán las siguientes:

   ![](assets/s_user_segmentation_scheduler3.png)

1. Defina el periodo de validez de la programación o especifique cuántas veces se va a ejecutar.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Compruebe la configuración y haga clic en **[!UICONTROL Finish]** para guardar.

   ![](assets/s_user_segmentation_scheduler5.png)
