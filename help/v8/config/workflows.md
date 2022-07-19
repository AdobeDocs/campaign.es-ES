---
title: Administrar y automatizar procesos con flujos de trabajo de Adobe Campaign
description: Introducción a los flujos de trabajo
feature: Workflows
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 59046a11c3e057cf41c322f190a9d8aef310c356
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 19%

---

# Administrar y automatizar procesos

Configure Campaign para aprovechar las potentes capacidades de automatización de campañas de marketing.

Puede configurar:

* Flujos de trabajo
* Campañas recurrentes
* Ciclo de validación completo
* Alertas
* Envío automático de informes
* Eventos activados

## Diseño y uso de flujos de trabajo{#gs-ac-wf}

Utilice los flujos de trabajo de Adobe Campaign para mejorar la velocidad y la escala de cada aspecto de las campañas de marketing, desde la creación de segmentos y la preparación de mensajes hasta la entrega.

Aprenda a diseñar flujos de trabajo en estos [casos de uso end-to-end](#end-to-end-uc).

Obtenga más información sobre los flujos de trabajo, la interfaz de usuario y la ejecución en estas páginas:

* [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html)

* [Prácticas recomendadas de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html)

* [Flujos de trabajo técnicos integrados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html)

* [Monitorización de la ejecución de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html)

* [Crear una audiencia en un flujo de trabajo de campaña de marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html)

## Actividades de flujo de trabajo {#wf-activities}

Obtenga más información sobre las actividades de flujo de trabajo disponibles en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html)

Las actividades de flujo de trabajo se agrupan por categoría. Están disponibles las cuatro categorías de actividad:

* [Actividades de segmentación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html): Consulta, lista de lectura, enriquecimiento, unión, etc.
* [Actividades de control de flujo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html): Planificador, ramificación, alerta, señal externa, etc.
* [Actividades de acción](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html): Envíos multicanal, código JavaScript, actividades CRM, Actualizar acumulado, etc.
* [Actividades de evento](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html): Transferencia de archivos, descarga de web y más

### Cambiar la actividad de la fuente de datos {#change-data-source-activity}

La actividad **[!UICONTROL Change data source]** permite cambiar la fuente de datos de un flujo de trabajo **[!UICONTROL Working table]**. Esto proporciona más flexibilidad para administrar los datos en diferentes fuentes de datos, como FDA, FFDA y bases de datos locales.

La **[!UICONTROL Working table]** permite que el flujo de trabajo de Adobe Campaign gestione datos y los comparta con las actividades de flujo de trabajo.
De forma predeterminada, la **[!UICONTROL Working table]** se crea en la misma base de datos que el origen de los datos que consultamos.

Por ejemplo, al consultar la tabla **[!UICONTROL Profiles]**, almacenada en la base de datos en la nube, creará un **[!UICONTROL Working table]** en la misma base de datos en la nube.
Para cambiar esto, puede añadir la actividad **[!UICONTROL Change Data Source]** para elegir una fuente de datos diferente para su **[!UICONTROL Working table]**.

Tenga en cuenta que al utilizar la actividad **[!UICONTROL Change Data Source]**, deberá volver a la base de datos en la nube para continuar con la ejecución del flujo de trabajo.

Para utilizar la actividad **[!UICONTROL Change Data Source]**:

1. Cree un flujo de trabajo.

1. Consulte los destinatarios objetivo con una actividad **[!UICONTROL Query]**.

   Para obtener más información sobre **[!UICONTROL Query]** actividad, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).

1. En el **[!UICONTROL Targeting]** , agregue **[!UICONTROL Change data source]** actividad y haga doble clic en ella para seleccionar **[!UICONTROL Default data source]**.

   La tabla de trabajo, que contiene el resultado de la consulta, se mueve a la base de datos predeterminada PostgreSQL.

1. En la pestaña **[!UICONTROL Actions]**, arrastre y suelte una actividad **[!UICONTROL JavaScript code]** para realizar operaciones unitarias en la tabla de trabajo.

   Para obtener más información sobre **[!UICONTROL JavaScript code]** actividad, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html).

1. Añada otra actividad **[!UICONTROL Change data source]** para volver a la base de datos en la nube.

   Haga doble clic en la actividad y seleccione **[!UICONTROL Active FDA external account]**, y luego escoja la cuenta externa  correspondiente.

1. Ahora puede iniciar el flujo de trabajo.

## Administrar almacenes virtuales {#warehouse}

Después de crear el flujo de trabajo, puede acceder a opciones adicionales con la variable **[!UICONTROL Properties]** para obtener más información sobre la configuración.

Más información sobre **Propiedades del flujo de trabajo** en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html).

En el **[!UICONTROL Execution]** del flujo de trabajo **[!UICONTROL Properties]**, puede elegir vincular el flujo de trabajo a diferentes almacenes y optimizar la administración de la carga de trabajo. Para obtener más información, consulte **Almacenes**, consulte [documentación del Snowflake](https://docs.snowflake.com/en/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

Según el propósito del flujo de trabajo, puede elegir entre los tres almacenes siguientes del **[!UICONTROL Warehouse]** lista desplegable:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: se establece de forma predeterminada al crear un nuevo flujo de trabajo.

* **[!UICONTROL Import / Export]**: debe configurarse con flujos de trabajo de importación o exportación para optimizar el rendimiento de las actividades.

* **[!UICONTROL Campaign Burst]**: debe configurarse con flujos de trabajo de campaña o de envíos para optimizar el tiempo de procesamiento de los envíos.

>[!NOTE]
>
>La variable **[!UICONTROL System]** el almacén solo está configurado para flujos de trabajo integrados.

## Configuración de campañas recurrentes

Diseñe un flujo de trabajo recurrente y cree una nueva instancia de envío cada vez que se ejecute el flujo de trabajo. Por ejemplo, si el flujo de trabajo está diseñado para ejecutarse una vez a la semana, el resultado sería 52 envíos después de un año. Esto también significa que los registros se separarán por cada instancia de envío.

Obtenga información sobre cómo crear una campaña recurrente en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html)


## Aprovechar los eventos de déclencheur

Utilice la mensajería transaccional de Campaign para automatizar los mensajes generados a partir de eventos activados desde sistemas de información. Estos mensajes transaccionales pueden ser factura, confirmación de pedido, confirmación de envío, cambio de contraseña, notificación de no disponibilidad del producto, extracto de cuenta o creación de cuenta de sitio web, por ejemplo. Estos mensajes se pueden enviar de forma individual o en lote por correo electrónico, SMS o notificaciones push.

![](../assets/do-not-localize/glass.png) Obtenga más información sobre las funcionalidades de mensajería transaccional en [esta sección](../send/transactional.md).

Conecte Adobe Campaign y Adobe Analytics para recuperar acciones de usuario y enviar mensajes personalizados casi en tiempo real.

![](../assets/do-not-localize/glass.png) Aprenda a integrar Campaign con otras soluciones en [esta sección](../start/connect.md)


## Casos de uso de extremo a extremo del flujo de trabajo{#end-to-end-uc}

En esta sección, encontrará varios casos de uso que aprovechan las capacidades de los Flujos de trabajo de Campaign.

### Entregas {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Envío de un correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html)

   Este caso de uso detalla cómo planificar la entrega de un correo electrónico recurrente a una lista de destinatarios en el día de su cumpleaños.

* [Cargar contenido de entrega](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html)
Cuando el contenido de su envío está disponible en un archivo HTML ubicado en un servidor remoto, puede cargar fácilmente este contenido en los envíos de Adobe Campaign.

* [Flujo de trabajo de entrega por canales cruzados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)
Obtenga información sobre cómo crear un flujo de trabajo de envío entre canales. El objetivo es segmentar una audiencia de los destinatarios de la base de datos en grupos diferentes y enviar un correo electrónico al primer grupo y un SMS al otro.

* [Enriquecimiento de correo electrónico con campos de datos personalizados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)
Aprenda a enviar un correo electrónico con campos de datos personalizados a perfiles que celebran su cumpleaños este mes. El correo electrónico incluirá un cupón válido una semana antes y después de su cumpleaños.

Y estas páginas en la documentación de Campaign v7:

* [Automatizar la creación, edición y publicación de contenido](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html){target=&quot;_blank&quot;} Obtenga información sobre cómo automatizar la creación y el envío de un bloque de contenido con el complemento Gestión de contenido de Campaign.

* [Pruebas A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html){target=&quot;_blank&quot;} Obtenga información sobre cómo comparar dos contenidos de envíos de correo electrónico a través de un flujo de trabajo de objetivos. El mensaje y el texto son idénticos en ambos envíos: solo cambia el diseño. La población objetivo se divide en tres: dos grupos de prueba y la población restante. Se envía una versión diferente a cada grupo de prueba.

### Monitorización {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Enviar un informe a una lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html)
Obtenga información sobre cómo generar un informe mensual integrado Tracking indicators en formato de PDF y enviarlo a una lista de operadores de Campaign.

* [Supervisión de los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html)
Aprenda a crear un flujo de trabajo que le permita monitorizar el estado de un conjunto de flujos de trabajo que estén &quot;en pausa&quot;, &quot;detenidos&quot; o &quot;con errores&quot;.

* [Envío de alertas personalizadas a operadores](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html)
Aprenda a enviar una alerta a un operador que contendrá el nombre de los perfiles que abrieron una newsletter pero que no hicieron clic en el vínculo que contenía.

### Administración de datos {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinación de actualizaciones de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html)
Obtenga información sobre cómo comprobar que el proceso de actualización ha finalizado antes de ejecutar otra operación de actualización. Para ello, se configura una variable de instancia y se deja que el flujo de trabajo pruebe si la instancia se está ejecutando para decidir si continuar con la ejecución del flujo de trabajo y realizar la actualización.

* [Crear una lista de resumen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html)
Aprenda a crear un flujo de trabajo que, después de recopilar archivos y de seguir varios enriquecimientos, le permita crear una lista de resumen. El ejemplo se basa en una lista de contactos que realizaron compras en una tienda.

* [Enriquecimiento de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html)
Aprenda a enviar envíos personalizados a perfiles que participaron en la competición más reciente en función de su puntuación.

* [Usar agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html)
Obtenga información sobre cómo identificar los últimos destinatarios agregados a la base de datos.

* [Actualización de lista trimestral con una consulta incremental](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html)
Aprenda a utilizar una consulta incremental para actualizar automáticamente una lista de destinatarios.

* [Configuración de un flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html)
Aprenda a diseñar un flujo de trabajo que se pueda reutilizar para importar perfiles procedentes de un CRM en la base de datos de Adobe Campaign.

### Direccionamiento {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consultar la tabla de destinatarios](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html)
Obtenga información sobre cómo recuperar los nombres y correos electrónicos de los destinatarios cuyo dominio de correo electrónico es &quot;orange.co.uk&quot; y que no viven en Londres.

* [Información de envío de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html)
Aprenda a definir consultas sobre la información de envío para recuperar el comportamiento del perfil.

* [Calcular agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html)
Aprenda a contar la cantidad de perfiles que viven en Londres, según el sexo.

* [Consulta con una relación de varios a varios](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html)
Obtenga información sobre cómo encontrar perfiles no contactados durante los últimos 7 días.

* [Llame a una variable de instancia en una consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html)
Aprenda a utilizar una variable de instancia para calcular dinámicamente el porcentaje dividido que se aplicará a una población.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

