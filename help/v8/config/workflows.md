---
title: Administración y automatización de procesos con flujos de trabajo de Adobe Campaign
description: Introducción a los flujos de trabajo
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 5%

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

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=es){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=es){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

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

Descubra los casos de uso que aprovechan las capacidades [de los flujos de trabajo de Campaign en esta sección](../../automation/workflow/workflow-use-cases.md).
