---
product: campaign
title: Prácticas recomendadas con flujos de trabajo
description: Descubra las prácticas recomendadas del flujo de trabajo Campaña
feature: Workflows
exl-id: 8bcaf367-5b1f-4d31-80c9-c77df43c6ed1
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 85%

---

# Prácticas recomendadas con flujos de trabajo{#workflow-best-practices}

A continuación se enumeran las directrices generales para optimizar el rendimiento del flujo de trabajo de Campaign, mejorar el diseño del flujo de trabajo y seleccionar la configuración correcta.

## Carpetas de flujo de trabajo {#workflow-folders}

Adobe recomienda crear los flujos de trabajo en una carpeta específica.

Si el flujo de trabajo afecta a toda la plataforma (a los procesos de limpieza, por ejemplo), una opción sería añadir una subcarpeta a la carpeta integrada **[!UICONTROL Technical Workflows]**.

## Nombre del flujo de trabajo {#workflow-naming}

Para facilitarle la búsqueda y la resolución de problemas si no funcionan de la forma esperada, Adobe recomienda dar nombres propios a los flujos de trabajo y a las etiquetas: rellene el campo de descripción del flujo de trabajo para resumir el proceso a realizar de modo que el operador pueda entenderlo fácilmente.

Si el flujo de trabajo forma parte de un proceso que incluye varios flujos de trabajo, puede ser explícito al introducir una etiqueta; el uso de números es una forma magnífica de ordenar los flujos de trabajo (por etiqueta).

Por ejemplo:

* 001: Importación: Importar destinatarios
* 002: Importación: Importar ventas
* 003: Importación: Importar detalles de ventas
* 010: Exportación: Exportar registros de entrega
* 011: Exportación: Exportar registros de seguimiento

## Intensidad del flujo de trabajo {#workflow-severity}

Puede configurar la gravedad de un flujo de trabajo en las propiedades de flujo de trabajo, en la pestaña **[!UICONTROL Execution]**:

* Normal
* Producción
* Importante

Proporcionar esta información al crear un flujo de trabajo le permite comprender la gravedad del proceso configurado.

Esta opción no afecta a nivel funcional a los flujos de trabajo que no sean flujos de trabajo de la campaña.

Los flujos de trabajo de la campaña (los flujos de trabajo creados como parte de una campaña u operación) con una gravedad mayor se ejecutan en el caso de que la campaña tenga muchos procesos que deberían ejecutarse simultáneamente. De manera predeterminada, solo se pueden ejecutar 10 procesos simultáneamente en una campaña, según la opción NmsOperation_LimitConcurrency. Por ejemplo, si una campaña contiene 25 flujos de trabajo, los flujos de trabajo con una gravedad más alta se ejecutan en el primer grupo de 10 procesos.

## Monitorización de flujos de trabajos {#workflow-monitoring}

Todos los flujos de trabajo programados que se ejecuten en entornos de producción se deben monitorizar para obtener un aviso en caso de error.

En las propiedades del flujo de trabajo, seleccione un grupo de Supervisor, ya sean los **[!UICONTROL Workflow supervisors]** predeterminados o un grupo personalizado. Asegúrese de que al menos un operador pertenece a este grupo y que su perfil incluye un correo electrónico.

Antes de empezar a crear un flujo de trabajo, recuerde establecer los supervisores del flujo de trabajo. Se les notifica por correo electrónico en caso de errores. Para obtener más información, consulte [Administración de errores](monitor-workflow-execution.md#managing-errors).

Compruebe con regularidad la pestaña **[!UICONTROL Monitoring]** para ver el estado general de los flujos de trabajo activos. Para obtener más información, consulte [Supervisión de instancias](monitor-workflow-execution.md#instance-supervision).

El HeatMap de flujo de trabajo permite a los administradores de la plataforma de Adobe Campaign controlar la carga en la instancia y planificar los flujos de trabajo en consecuencia. Para obtener más información, consulte [Monitoreo de flujos de trabajo](heatmap.md).

## Actividades {#using-activities}

>[!CAUTION]
>
>Puede copiar y pegar actividades en un mismo flujo de trabajo. Sin embargo, no se recomienda copiar y pegar actividades en diferentes flujos de trabajo. Algunas configuraciones asociadas a actividades como Deliveries y Scheduler podrían provocar conflictos y errores al ejecutar el flujo de trabajo de destino. En su lugar, le recomendamos que **duplique** los flujos de trabajo. Para obtener más información, consulte [Duplicación de flujos de trabajo](build-a-workflow.md#duplicate-workflows).

### Nombre de la actividad {#name-of-the-activity}

Al desarrollar el flujo de trabajo, todas las actividades tienen un nombre, como todos los objetos de Adobe Campaign. Aunque la herramienta genera el nombre, le recomendamos que cambie el nombre por uno explícito al configurarlo. El riesgo de hacerlo más tarde es que puede interrumpir el flujo de trabajo con actividades al usar el nombre de otra actividad anterior. Por lo tanto, sería difícil actualizar los nombres más adelante.

El nombre de la actividad se puede encontrar en la pestaña **[!UICONTROL Advanced]**. Evite poner nombres como **[!UICONTROL query]**, **[!UICONTROL query1]**, **[!UICONTROL query11]**; asígneles nombres explícitos como **[!UICONTROL querySubscribedRecipients]**. Este nombre se muestra en el historial y, si procede, en los registros SQL, lo que le ayuda a depurar el flujo de trabajo al configurarlo.

### Primeras y últimas actividades {#first-and-last-activities}

* Inicie siempre el flujo de trabajo con una actividad **[!UICONTROL Start]** o una actividad **[!UICONTROL Scheduler]**. Si es relevante, también puede utilizar una actividad **[!UICONTROL External signal]**.
* Al crear el flujo de trabajo, utilice solamente una actividad **[!UICONTROL Scheduler]** por rama. Si la misma rama de un flujo de trabajo tiene varios planificadores (vinculados entre sí), el número de tareas que se van a ejecutar se multiplica exponencialmente, lo cual sobrecarga considerablemente la base de datos. Esta regla también se aplica para todas las actividades con una pestaña de **[!UICONTROL Scheduling & History]**. Más información sobre [Programación](scheduler.md).

   ![](assets/wf-scheduler.png)

* Utilice las actividades **[!UICONTROL End]** para cada flujo de trabajo. Esto permite a Adobe Campaign liberar espacio temporal utilizado para los cálculos dentro de los flujos de trabajo. Para obtener más información, consulte [Inicio y finalización](start-and-end.md).

### Javascript dentro de una actividad {#javascript-within-an-activity}

Quizá desee añadir JavaScript al iniciar una actividad de flujo de trabajo. Puede hacerlo mediante la pestaña **[!UICONTROL Advanced]** de la actividad.

Para simplificar la identificación del flujo de trabajo, se recomienda utilizar guiones dobles al principio y al final de la etiqueta de actividad como se indica a continuación: -- Mi etiqueta --.

### Señal {#signal}

La mayor parte del tiempo no sabrá desde dónde se llama a la señal. Para evitar este problema, utilice el campo **[!UICONTROL Comment]** dentro de la pestaña **[!UICONTROL Advanced]** de la actividad de señal para documentar el origen esperado de una señal para esta actividad.

## Actualizaciones de flujo de trabajo {#workflow-update}

Un flujo de trabajo de producción no se debe actualizar directamente. A menos que el proceso consista en crear una campaña con flujos de trabajo de plantilla, los procesos deben probarse primero en un entorno de desarrollo. Después de esta validación, el flujo de trabajo se puede implementar e iniciar en la producción.

Realice todas las pruebas en entornos de desarrollo o ensayo, no en entornos de producción. En ese caso no se puede garantizar el rendimiento.

Los flujos de trabajo archivados pueden permanecer en plataformas de desarrollo o prueba, en una carpeta archivada, pero el entorno de producción debe permanecer lo más limpio posible. Los flujos de trabajo antiguos deben eliminarse del entorno de producción si están inactivos.

## Ejecución y rendimiento {#execution-and-performance}

### Registros {#logs}

El método JavaScript **[!UICONTROL logInfo()]** es una solución para depurar un flujo de trabajo. Sin embargo, debe utilizarse con cuidado, especialmente para actividades que se ejecutan con frecuencia: puede sobrecargar los registros y aumentar significativamente el tamaño de la tabla de registro.

### Mantener poblaciones provisionales

El **Mantener el resultado de poblaciones provisionales entre dos ejecuciones** mantiene las tablas temporales entre dos ejecuciones de un flujo de trabajo.

Está disponible en la pestaña **[!UICONTROL General]** de las propiedades del flujo de trabajo y se puede utilizar para fines de desarrollo y prueba para controlar los datos y comprobar los resultados. Puede utilizar esta opción en entornos de desarrollo, pero nunca en entornos de producción. Si mantiene las tablas temporales, el tamaño de la base de datos puede aumentar significativamente y finalmente alcanzar el límite de tamaño. Además, ralentiza la copia de seguridad.

Solo se conservan las tablas de trabajo de la última ejecución del flujo de trabajo. El flujo de trabajo **[!UICONTROL cleanup]**, que se ejecuta diariamente, depura todas las tablas de trabajo de ejecuciones previas.

>[!CAUTION]
>
>Esta opción **nunca** se debe marcar en un flujo de trabajo de **producción**. Esta opción se utiliza para analizar los resultados y está diseñada únicamente para fines de prueba y, por lo tanto, solo debe usarse en entornos de ensayo o desarrollo.


### Registrar consultas SQL

El **Registrar consultas SQL en el historial** está disponible en la **[!UICONTROL Execution]** de las propiedades del flujo de trabajo. Esta opción registra todas las consultas SQL de las diferentes actividades y proporciona una forma de ver qué ejecuta realmente la plataforma. Sin embargo, esta opción solo debe utilizarse **temporalmente** durante el desarrollo y **no activado en producción**.

La práctica recomendada es purgar los registros cuando ya no los necesite. El historial del flujo de trabajo no se purga automáticamente: todos los mensajes se mantienen de forma predeterminada. El historial se puede eliminar a través del menú **[!UICONTROL File > Actions]** o haciendo clic en el botón Actions ubicado en la barra de herramientas situada encima de la lista. Seleccione Purge history.
Para aprender a purgar los registros, consulte esta [documentación](start-a-workflow.md).

### Planificación de flujo de trabajo {#workflow-planning}

Se deben aplicar prácticas recomendadas adicionales en la planificación de la ejecución de los flujos de trabajo para evitar problemas:

* Mantenga un nivel estable de actividad a lo largo del día y evite los picos para evitar que la instancia se sobrecargue. Para ello, distribuya los tiempos de inicio del flujo de trabajo de forma uniforme a lo largo del día.
* Programe la carga de datos durante la noche para reducir la contención de recursos.
* Los flujos de trabajo largos pueden tener un impacto en los recursos de servidor y de base de datos. Divida los flujos de trabajo más largos para reducir el tiempo de procesamiento.
* Para reducir los tiempos de ejecución generales, reemplace las actividades largas con actividades simplificadas y más rápidas.
* Evite ejecutar más de 20 flujos de trabajo simultáneamente. Cuando se ejecutan demasiados flujos de trabajo al mismo tiempo, la plataforma puede sobrecargarse y volverse inestable.

### Ejecución del flujo de trabajo {#workflow-execution}

Mejore la estabilidad de las instancias mediante la implementación de las siguientes prácticas recomendadas:

* **No programe un flujo de trabajo para que se ejecute con una frecuencia superior a 15 minutos**, ya que podría limitar el rendimiento general del sistema y crear bloques en la base de datos.

* **Asimismo, evite dejar los flujos de trabajo en estado pausado**. Si crea un flujo de trabajo temporal, asegúrese de que este pueda terminar correctamente y no permanecer en estado **[!UICONTROL paused]**. Si está en pausa, eso implica que necesita mantener las tablas temporales y, por lo tanto, aumentar el tamaño de la base de datos. Asigne supervisores de flujo de trabajo en Workflow Properties para enviar una alerta cuando un flujo de trabajo falle o el sistema lo ponga en pausa.

   Para evitar tener flujos de trabajo en estado pausado:

   * Consulte los flujos de trabajo regularmente para garantizar que no hay errores inesperados.
   * Mantenga los flujos de trabajo tan sencillos como sea posible, por ejemplo, dividiendo los flujos de trabajo grandes en distintos flujos de trabajo. Puede utilizar las actividades **[!UICONTROL External signal]** impulsando la ejecución en función de la ejecución de otros flujos de trabajo.
   * Evite tener actividades desactivadas con flujos en los flujos de trabajo, dejando los subprocesos abiertos y generando que muchas tablas temporales puedan consumir mucho espacio. Evite mantener las actividades en estados **[!UICONTROL Do not enable]** o **[!UICONTROL Enable but do not execute]** en los flujos de trabajo.

* **Detenga los flujos de trabajo no utilizados**. Los flujos de trabajo que siguen ejecutándose mantienen conexiones con la base de datos.

* **Solo se debe utilizar la detención incondicional en los casos más inusuales**. Evite utilizar esta acción de forma regular. El no realizar un cierre limpio de las conexiones generadas por los flujos de trabajo a la base de datos afecta al rendimiento.

* **No realice varias solicitudes de detención en el mismo flujo de trabajo**. La detención de un flujo de trabajo es un proceso asíncrono: la solicitud se registra y, después, el servidor o los servidores de flujo de trabajo cancelan las operaciones en curso. Por lo tanto, la detención de una instancia de flujo de trabajo puede llevar tiempo, especialmente si el flujo de trabajo se ejecuta en varios servidores, cada uno de los cuales debe asumir el control para cancelar las tareas en curso. Para evitar cualquier problema, espere a que se complete la operación de parada y evite detener un flujo de trabajo varias veces.

### Ejecutar en la opción de motor {#execute-in-the-engine-option}

En un entorno de producción, evite ejecutar flujos de trabajo en el motor. Si la variable **[!UICONTROL Execute in the engine]** está marcada en la **[!UICONTROL Workflow properties]** Sin embargo, el flujo de trabajo tiene prioridad y el motor de flujos de trabajo detiene todo el resto de flujos de trabajo hasta que este haya terminado.

![](assets/wf-execute-in-engine.png)
