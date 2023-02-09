---
product: campaign
title: Coordinación de actualizaciones de datos
description: Coordinación de actualizaciones de datos
feature: Workflows, Data Management
exl-id: 9faf7ee7-07c1-415b-b234-a945994792c7
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# Coordinación de actualizaciones de datos{#coordinating-data-updates}



Este caso de uso detalla la creación de un flujo de trabajo que permite administrar las actualizaciones integradas simultáneas cuando se utilizan varias ejecuciones de un flujo de trabajo.

El objetivo es comprobar que el proceso de actualización ha finalizado antes de ejecutar otra operación de actualización. Para ello, se configura una variable de instancia y se deja que el flujo de trabajo pruebe si la instancia se está ejecutando para decidir si continuar o no con la ejecución del flujo de trabajo y realizar la actualización.

![](assets/uc_dataupdate_wkf.png)

Este flujo de trabajo consta de:

* una actividad **Planificador**, que ejecuta el flujo de trabajo en una frecuencia específica.
* una actividad **Prueba** que comprueba si el flujo de trabajo ya se está ejecutando.
* Las actividades **Consulta** y **Actualización de datos** en caso de que el flujo de trabajo no se esté ejecutando, seguidas de una actividad **Fin** que reinicia la variable de la instancia de flujo de trabajo en falso.
* Una actividad **Fin** si el flujo de trabajo ya se está ejecutando.

Para crear un flujo de trabajo, siga los pasos siguientes:

1. Agregue una actividad **Planificador** y, a continuación, configure su frecuencia según sus necesidades.
1. Agregue una actividad **Prueba** para comprobar si el flujo de trabajo ya se está ejecutando y, a continuación, configúrelo como se muestra a continuación.

   >[!NOTE]
   >
   >“isRunning” es el nombre de la variable de instancia que se ha elegido para este ejemplo. Esta no es una variable integrada.

   ![](assets/uc_dataupdate_test.png)

1. Agregue una actividad **Fin** a la bifurcación **No.** De este modo, no se ejecuta nada si el flujo de trabajo ya se está ejecutando.
1. Agregue las actividades deseadas a la bifurcación **Sí.** En este caso, las actividades **Consulta** y **Actualización de datos**
1. Abra la primera actividad y luego añada el comando **instance.vars.isRunning = true** en la pestaña **[!UICONTROL Advanced]**. De este modo, la variable de instancia se establece como en ejecución.

   ![](assets/uc_dataupdate_query.png)

1. Agregue una actividad **Fin** al final de la bifurcación **[!UICONTROL Yes]** luego añada el comando **instance.vars.isRunning = false** en la pestaña **[!UICONTROL Advanced]**.

   De este modo, no se ejecutará ninguna acción mientras se esté ejecutando el flujo de trabajo.

   ![](assets/uc_dataupdate_end.png)

**Temas relacionados:**

* [Prevención de las ejecuciones múltiples simultáneas](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)
* [Actividad Actualizar datos](update-data.md)
