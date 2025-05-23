---
title: Administración y automatización de procesos con flujos de trabajo de Adobe Campaign
description: Introducción a los flujos de trabajo
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 8e1401ef0aada30d941905936b45c6c1819c83a7
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 21%

---

# Introducción a los flujos de trabajo{#gs-with-workflows}

Configure Campaign para aprovechar las potentes funcionalidades de automatización de campañas de marketing.

Puede configurar lo siguiente:

* Flujos de trabajo
* Campañas recurrentes
* Ciclo de validación de extremo a extremo
* Alertas
* Envío automático de informes
* Eventos activados

>[!NOTE]
>
>La interfaz de usuario web de Adobe Campaign viene con un lienzo reinventado para los flujos de trabajo, lo que permite crear recorridos de cliente más dinámicos y personalizados. Para obtener más información sobre los flujos de trabajo para la interfaz de usuario web, consulte [Documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Diseñar y utilizar flujos de trabajo {#gs-ac-wf}

Utilice flujos de trabajo de Adobe Campaign para mejorar la velocidad y la escala de cada aspecto de sus campañas de marketing, desde la creación de segmentos y la preparación de mensajes hasta la entrega.

Aprenda a diseñar flujos de trabajo en estos [casos de uso de extremo a extremo](#end-to-end-uc).

Obtenga más información sobre los flujos de trabajo de la interfaz de usuario y la ejecución en estas páginas:

* [Introducción a los flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es){target="_blank"}

* [Prácticas recomendadas de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=es){target="_blank"}

* [Flujos de trabajo técnicos integrados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=es){target="_blank"}

* [Supervisar la ejecución de flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=es){target="_blank"}

* [Crear una audiencia en un flujo de trabajo de campaña de marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=es){target="_blank"}

## Actividades de flujo de trabajo {#wf-activities}

Obtenga más información acerca de las actividades de flujo de trabajo disponibles en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=es){target="_blank"}

Las actividades de flujo de trabajo se agrupan por categoría. Hay cuatro categorías de actividades disponibles:

* [Actividades de segmentación](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=es){target="_blank"}: consulta, lista de lectura, enriquecimiento, unión y más
* [Actividades de control de flujo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=es){target="_blank"}: Planificador, Bifurcación, Alerta, Señal externa y más
* [Actividades de acción](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=es){target="_blank"}: envíos en canales múltiples, código JavaScript, actividades CRM, acumulado de actualización y más
* [Actividades de eventos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=es){target="_blank"}: transferencia de archivos, descarga web y más

### Actividad para cambiar la fuente de datos {#change-data-source-activity}

La actividad **[!UICONTROL Change data source]** permite cambiar la fuente de datos de un flujo de trabajo **[!UICONTROL Working table]**. Esto proporciona más flexibilidad para administrar los datos en diferentes fuentes de datos, como FDA, FFDA y bases de datos locales.

**[!UICONTROL Working table]** permite que el flujo de trabajo de Adobe Campaign administre datos y los comparta con las actividades de flujo de trabajo.
De forma predeterminada, la **[!UICONTROL Working table]** se crea en la misma base de datos que el origen de los datos que consultamos.

Por ejemplo, al consultar la tabla **[!UICONTROL Profiles]**, almacenada en la base de datos en la nube, creará un **[!UICONTROL Working table]** en la misma base de datos en la nube.
Para cambiar esto, puede añadir la actividad **[!UICONTROL Change Data Source]** para elegir una fuente de datos diferente para su **[!UICONTROL Working table]**.

Tenga en cuenta que al utilizar la actividad **[!UICONTROL Change Data Source]**, deberá volver a la base de datos en la nube para continuar con la ejecución del flujo de trabajo.

Para utilizar la actividad **[!UICONTROL Change Data Source]**:

1. Cree un flujo de trabajo.

1. Consulte los destinatarios objetivo con una actividad **[!UICONTROL Query]**.

   Para obtener más información sobre la actividad **[!UICONTROL Query]**, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}.

1. En la ficha **[!UICONTROL Targeting]**, agregue una actividad **[!UICONTROL Change data source]** y haga doble clic en ella para seleccionar **[!UICONTROL Default data source]**.

   La tabla de trabajo, que contiene el resultado de la consulta, se mueve a la base de datos predeterminada PostgreSQL.

1. En la pestaña **[!UICONTROL Actions]**, arrastre y suelte una actividad **[!UICONTROL JavaScript code]** para realizar operaciones unitarias en la tabla de trabajo.

   Para obtener más información sobre la actividad **[!UICONTROL JavaScript code]**, consulte [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=es){target="_blank"}.

1. Añada otra actividad **[!UICONTROL Change data source]** para volver a la base de datos en la nube.

   Haga doble clic en la actividad y seleccione **[!UICONTROL Active FDA external account]**, a continuación, seleccione la cuenta externa correspondiente.

1. Ahora puede iniciar el flujo de trabajo.

## Administración de almacenes virtuales {#warehouse}

Después de crear el flujo de trabajo, puede acceder a opciones adicionales con el botón **[!UICONTROL Properties]** para realizar más configuraciones.

Obtenga más información acerca de **propiedades del flujo de trabajo** en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=es){target="_blank"}.

Desde la pestaña **[!UICONTROL Execution]** de **[!UICONTROL Properties]** de su flujo de trabajo, puede elegir vincular el flujo de trabajo a diferentes almacenes y optimizar la administración de la carga de trabajo. Para obtener más información sobre **Almacenes**, consulte la [documentación de Snowflake](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Según el propósito del flujo de trabajo, puede elegir entre los tres almacenes siguientes de la lista desplegable **[!UICONTROL Warehouse]**:

* **[!UICONTROL Default]** / **[!UICONTROL Campaign]**: establecido de forma predeterminada al crear un nuevo flujo de trabajo.

* **[!UICONTROL Import / Export]**: debe configurarse con flujos de trabajo de importación o exportación para optimizar el rendimiento de las actividades.

* **[!UICONTROL Campaign Burst]**: debe configurarse con los flujos de trabajo de campañas o envíos para optimizar el tiempo de procesamiento de los envíos.

>[!NOTE]
>
>El almacén **[!UICONTROL System]** solo está establecido para flujos de trabajo integrados.

## Configuración de campañas recurrentes

Diseñe un flujo de trabajo recurrente y cree una nueva instancia de envío cada vez que se ejecute el flujo de trabajo. Por ejemplo, si el flujo de trabajo está diseñado para ejecutarse una vez a la semana, el resultado sería de 52 envíos al cabo de un año. Esto también significa que los registros se separarán por cada instancia de envío.

Aprenda a crear una campaña recurrente en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=es){target="_blank"}.


## Aprovechamiento de eventos de déclencheur

Utilice la mensajería transaccional de Campaign para automatizar los mensajes generados a partir de eventos activados desde sistemas de información. Estos mensajes transaccionales pueden ser facturas, confirmaciones de pedidos, confirmaciones de envío, cambios de contraseña, notificaciones de no disponibilidad de productos, extractos de cuentas o creación de cuentas en sitios web, por ejemplo. Estos mensajes se pueden enviar por separado o en lote por correo electrónico, SMS o notificaciones push.

Obtenga más información acerca de las funcionalidades de mensajería transaccional en [esta sección](../send/transactional.md).

Conecte Adobe Campaign y Adobe Analytics para recuperar las acciones del usuario y enviar mensajes personalizados casi en tiempo real.

Aprenda a integrar Campaign con otras soluciones en [esta sección](../start/connect.md)


## Casos de uso de extremo a extremo del flujo de trabajo{#end-to-end-uc}

En esta sección, encontrará varios casos de uso que aprovechan las capacidades de los Flujos de trabajo de Campaign.

### Envíos {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Envío de un correo electrónico de cumpleaños](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=es){target="_blank"}

  Este caso de uso detalla cómo planificar la entrega de un correo electrónico recurrente a una lista de destinatarios en el día de su cumpleaños.

* [Cargar contenido de envío](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=es){target="_blank"}
Cuando el contenido de la entrega está disponible en un archivo HTML ubicado en un servidor remoto, puede cargar fácilmente este contenido en las entregas de Adobe Campaign.

* [Flujo de trabajo de entrega por canales cruzados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=es){target="_blank"}
Obtenga información sobre cómo crear un flujo de trabajo de entrega multicanal. El objetivo es segmentar una audiencia de los destinatarios de la base de datos en diferentes grupos y enviar un correo electrónico al primer grupo y un SMS al otro.

* [Enriquecimiento de correo electrónico con campos de fecha personalizados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=es){target="_blank"}
Aprenda a enviar un correo electrónico con campos de datos personalizados a perfiles que celebran su cumpleaños este mes. El correo electrónico incluirá un cupón válido una semana antes y después de su cumpleaños.

Y estas páginas en la documentación de Campaign v7:

* [Creación, edición y publicación automática de contenido](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=es){target="_blank"}
Obtenga información sobre cómo automatizar la creación y el envío de un bloque de contenido con el complemento de gestión de contenido de Campaign.

* [Pruebas A/B](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=es){target="_blank"}
Obtenga información sobre cómo comparar dos contenidos de entrega por correo electrónico a través de un flujo de trabajo de objetivo. El mensaje y el texto son idénticos en ambos envíos: solo cambia el diseño. La población objetivo se divide en tres: dos grupos de prueba y la población restante. Se envía una versión diferente a cada grupo de prueba.

### Monitorización {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Enviar un informe a una lista](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=es){target="_blank"}
Obtenga información sobre cómo generar un informe mensual integrado de indicadores de seguimiento en formato PDF y enviarlo a una lista de operadores de Campaign.

* [Supervise sus flujos de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=es){target="_blank"}
Obtenga información sobre cómo crear un flujo de trabajo que le permita monitorizar el estado de un conjunto de flujos de trabajo que están &quot;en pausa&quot;, &quot;detenidos&quot; o &quot;con errores&quot;.

* [Enviar alertas personalizadas a operadores](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=es){target="_blank"}
Obtenga información sobre cómo enviar una alerta a un operador que contendrá el nombre de los perfiles que abrieron un boletín informativo, pero que no hicieron clic en el vínculo que contenía.

### Administración de datos {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordinar actualizaciones de datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=es){target="_blank"}
Obtenga información sobre cómo comprobar que el proceso de actualización ha finalizado antes de ejecutar otra operación de actualización. Para ello, se configura una variable de instancia y se deja que el flujo de trabajo pruebe si la instancia se está ejecutando para decidir si continuar con la ejecución del flujo de trabajo y realizar la actualización.

* [Crear una lista de resumen](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=es){target="_blank"}
Obtenga información sobre cómo crear un flujo de trabajo que, después de recopilar archivos y luego de varios enriquecimientos, le permita crear una lista de resumen. El ejemplo se basa en una lista de contactos que realizaron compras en una tienda.

* [Enriquecer datos](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=es){target="_blank"}
Aprenda a realizar envíos personalizados a perfiles que participaron en la competición más reciente según su puntuación.

* [Usar agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=es){target="_blank"}
Obtenga información sobre cómo identificar los últimos destinatarios agregados a la base de datos.

* [Actualización de lista trimestral con una consulta incremental](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=es){target="_blank"}
Obtenga información sobre cómo utilizar una consulta incremental para actualizar automáticamente una lista de destinatarios.

* [Configurar un flujo de trabajo de importación recurrente](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=es){target="_blank"}
Aprenda a diseñar un flujo de trabajo que se pueda reutilizar para importar perfiles procedentes de un CRM en la base de datos de Adobe Campaign.

### Direccionamiento {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Consulte la tabla de destinatarios](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=es){target="_blank"}
Obtenga información sobre cómo recuperar los nombres y correos electrónicos de los destinatarios cuyo dominio de correo electrónico es &quot;orange.co.uk&quot; y que no viven en Londres.

* [Información de envío de consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=es){target="_blank"}
Obtenga información sobre cómo definir consultas en la información de envío para recuperar el comportamiento del perfil.

* [Calcular agregados](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=es){target="_blank"}
Aprenda a contar el número de perfiles que viven en Londres, según el sexo.

* [Consulta con una relación de varios a varios](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=es){target="_blank"}
Aprenda a encontrar perfiles no contactados durante los últimos 7 días.

* [Llamar a una variable de instancia en una consulta](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=es){target="_blank"}
Aprenda a utilizar una variable de instancia para calcular dinámicamente el porcentaje dividido que se aplicará a una población.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=es#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

