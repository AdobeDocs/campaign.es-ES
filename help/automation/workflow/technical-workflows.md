---
product: campaign
title: Flujos de trabajo técnicos
description: Obtenga más información sobre los flujos de trabajo técnicos disponibles con Campaign
feature: Workflows
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '1667'
ht-degree: 92%

---

# Flujos de trabajo técnicos{#about-technical-workflows}

Adobe Campaign incluye un conjunto de flujos de trabajo técnicos integrados. Administran operaciones y trabajos programados para su ejecución periódica en el servidor. Permiten realizar el mantenimiento de la base de datos, reenviar la información de seguimiento de los envíos o configurar procesos provisionales relacionados con los envíos. Los flujos de trabajo técnicos se configuran mediante el nodo **[!UICONTROL Administration > Production > Technical workflows]**.

![](assets/navtree.png)

Hay plantillas nativas disponibles para crear flujos de trabajo técnicos. Se pueden configurar para adaptarlas a sus necesidades.

La subcarpeta **[!UICONTROL Campaign process]** centraliza los flujos de trabajo necesarios para ejecutar procesos en las campañas: notificación de tareas, administración de existencias, cálculo de costes, etc.

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>La lista de flujos de trabajo técnicos instalados con cada módulo está disponible en una [sección específica](technical-workflows.md).

Puede crear otros flujos de trabajo técnicos en el nodo **[!UICONTROL Administration > Production > Technical workflows]** de la estructura del árbol. Sin embargo, este proceso está reservado para usuarios expertos.

Las actividades ofrecidas son las mismas que para los flujos de trabajo de objetivos. [Más información](targeting-workflows.md)

Los flujos de trabajo detallados en esta sección se instalan con los distintos paquetes integrados de Adobe Campaign. Estos paquetes, y los flujos de trabajo técnicos relacionados, dependen del acuerdo de licencia.

De forma predeterminada, los flujos de trabajo técnicos están disponibles en una subcarpeta del siguiente nodo: **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

Tenga en cuenta que solo los operadores con permisos de administración pueden iniciar y modificar los flujos de trabajo técnicos.

>[!NOTE]
>
>Los flujos de trabajo técnicos relacionados con el complemento Centro de mensajes están disponibles de forma predeterminada en la **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technical workflows]** nodo.

Obtenga información sobre cómo monitorizar flujos de trabajo técnicos en esta [sección dedicada](monitor-technical-workflows.md).


## Lista de flujos de trabajo técnicos {#list-technical-workflows}

| Flujo de trabajo técnico | Paquete | Descripción |
|------|--------|-----------|
| **Limpieza de alias** (aliasCleansing) | Instalado de forma predeterminada | Este flujo de trabajo estandariza los valores de enumeración. Se activa cada día a las 3 de la mañana de forma predeterminada. |
| **Facturación** (facturación) | Instalado de forma predeterminada | Este flujo de trabajo envía el informe de actividad del sistema al operador “facturación” por correo electrónico. Se activa el día 25 de cada mes en la instancia de Marketing. |
| **Trabajos de Campaign** (operationMgt) | Instalado de forma predeterminada | Este flujo de trabajo administra los trabajos de las campañas de marketing (inicia la segmentación, la extracción de archivos, etc.). También crea flujos de trabajo relacionados con campañas recurrentes y periódicas. |
| **Recopilación de datos para el servicio HeatMap** (collectDataHeatMapService) | Instalado de forma predeterminada | Este flujo de trabajo recupera los datos requeridos por el servicio HeatMap. |
| **Recopilar solicitudes de privacidad** (collectPrivacyRequests) | Reglamento de protección de datos de privacidad | Este flujo de trabajo genera los datos del destinatario almacenados en Adobe Campaign y los hace disponibles para su descarga en la pantalla de la solicitud de privacidad. |
| **Cálculo de costes** (budgetMgt) | Instalado de forma predeterminada | Este flujo de trabajo inicia el cálculo de las líneas de gastos y de costes sobre presupuestos, planes, programas, campañas, envíos y tareas. |
| **Limpieza de base de datos** (cleanup) | Instalado de forma predeterminada | Este flujo de trabajo es el del mantenimiento de la base de datos: realiza diferentes cálculos en las estadísticas y procesos y elimina los datos obsoletos de la base de datos según la configuración definida en el asistente de implementación. Se activa cada día a las 4 a. m. de manera predeterminada. |
| **Eliminar usuarios de LINE bloqueados** (deleteBlockedLineUsersV2) | Canal LINE | Este flujo de trabajo garantiza que los datos de los usuarios de LINE V2 se eliminen después de haber bloqueado la cuenta oficial de LINE durante 180 días. |
| **Eliminar datos de solicitudes de privacidad** (deletePrivacyRequestsData) | Reglamento de protección de datos de privacidad | Este flujo de trabajo elimina los datos del destinatario almacenados en Adobe Campaign. |
| **Indicadores de envío** (deliveryIndicators) | Plataforma intermediaria | Este flujo de trabajo actualiza los indicadores de seguimiento de un envío para un envío. De forma predeterminada, este flujo de trabajo se activa cada hora. |
| **Procesos de marketing distribuido** (centralLocalMgt) | Marketing central/local (Marketing distribuido) | Este flujo de trabajo comienza con el proceso vinculado al uso del módulo de marketing distribuido. Inicia la creación de las campañas locales y gestiona las notificaciones vinculadas a los pedidos y a la disponibilidad del paquete de Campaign. |
| **Depuración de eventos** (webAnalyticsPurgeWebEvents) | Conectores de análisis web | Este flujo de trabajo permite eliminar todos los eventos del campo de base de datos según el periodo configurado en el campo Lifespan. |
| **Exportar audiencias a Adobe Experience Cloud** (exportSharedAudience) | Integración con Adobe Experience Cloud | Este flujo de trabajo exporta audiencias como audiencias o segmentos compartidos. Estas audiencias pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. |
| **Previsión**(previsión) | Entrega | Este flujo de trabajo analiza las entregadas guardadas en el calendario provisional (crea registros provisionales). Se activa cada día a la 1 de la mañana de forma predeterminada. |
| **Cálculo acumulado completo (cubo propositionrcp)** (agg_nmspropositionrcp_full) | Motor de ofertas (interacción) | Este flujo de trabajo actualiza el acumulado completo para el cubo Propuesta de oferta. Se activa todos los días a las 6 a. m. de manera predeterminada. Este acumulado captura las siguientes dimensiones: Canal, Envío, Oferta de marketing y Fecha. Luego se utiliza el cubo Propuesta de oferta para generar informes basados en ofertas. Puede obtener más información sobre los cubos en [esta sección](../../v8/reporting/gs-cubes.md). |
| **Identificación de contactos convertidos** (webAnalyticsFindConverted) | Conectores de análisis web | Este flujo de trabajo lista a los visitantes del sitio que han finalizado su compra después de la campaña de remarketing. Los datos recopilados por este flujo de trabajo se pueden consultar en el reporte de eficiencia de remarketing (consulte esta página). |
| **Importar audiencias desde Adobe Experience Cloud** (importSharedAudience) | Integración con Adobe Experience Cloud | Este flujo de trabajo permite importar audiencias y segmentos de distintas soluciones de Adobe Experience Cloud en Adobe Campaign. |
| **Trabajos en envíos en campañas** (deliveryMgt) | Instalado de forma predeterminada | Este flujo de trabajo activa los envíos aprobados e inicia el posprocesado del proveedor de servicios para un envío externo. También envía notificaciones de aprobación y recordatorios. |
| **Trabajos en proveedores de servicios** (supplierMgt) | Instalado de forma predeterminada | Este flujo de trabajo comienza a procesar el proveedor (correo electrónico al enrutador y posprocesado) una vez que se aprueban los envíos. |
| **Migración MID a LineUserID** (MIDToUserIDMigration) | Canal LINE | Este flujo de trabajo genera las ID de los usuarios de LINE V2 para la migración de LINE V1 a LINE V2. |
| **Centro de mensajes &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | Control de mensajes transaccionales (Centro de mensajes - Control) | Este flujo de trabajo: <ul><li>recupera la lista de eventos procesados por las operaciones.</li><li>se sincroniza con la tabla NmsBroadLogMsg para poder recuperar los atributos del mensaje de la entrega.</li><li>recupera los registros de envío de eventos en cuanto se completa la sincronización con la tabla NmsBroadLogMsg.</li><li>se sincroniza con la tabla NmsTrackingUrl para recuperar el seguimiento de las URL de la entrega.</li><li>recupera las URL de seguimiento de eventos en cuanto se completa la sincronización con la tabla NmsTrackingUrl.</li><li>permite recuperar todas las direcciones de correo electrónico puestas en cuarentena cada tres horas después de realizar una entrega.</li></ul> |
| **Cálculo acumulado completo de MessageCenter** (agg_messageCenter_full) | Control de mensajes transaccionales (Centro de mensajes - Control) | Este flujo de trabajo actualiza el acumulado completo para el cubo Centro de mensajes. Se activa cada día a las 3 de la mañana de forma predeterminada. Este acumulado captura las siguientes dimensiones: canal, fecha, estado y tipo de evento. Luego se utiliza el cubo Centro de mensajes para generar informes basados en eventos. Puede obtener más información sobre los cubos en  |
| **Intermediario (contadores de envíos)** (defaultMidSourcingDlv) | Transferir a Intermediario | Este flujo de trabajo recopila información de recuento para los envíos en el servidor intermediario. La información de recuento incluye indicadores de envío generales como el número de envíos realizados, etc. No se incluye la información de seguimiento como las aperturas. De forma predeterminada, se activa cada diez minutos. |
| **Intermediario (registros de envío)** (defaultMidSourcingLog) | Transferir a Intermediario | Este flujo de trabajo recopila los registros de envío en el servidor intermediario. Se activa cada hora de forma predeterminada. |
| **Administración de exclusión de NMAC** (mobileAppOptOutMgt) | Canal de aplicaciones móviles (Push) | Este flujo de trabajo actualiza las bajas de las notificaciones en los dispositivos móviles. Se activa cada 6 horas entre la medianoche y la 1 a. m. |
| **Notificación de ofertas** (offerMgt) | Instalado de forma predeterminada | Este flujo de trabajo implementa las ofertas aprobadas en el entorno en línea, así como todas las categorías incluidas en el catálogo de ofertas. |
| **Limpieza de flujos de trabajo en pausa** (cleanupPausedWorkflows) | Instalado de forma predeterminada | Este flujo de trabajo analiza los flujos de trabajo en pausa con opción de gravedad definida en normal y activa las advertencias y notificaciones cuando dichos flujos llevan demasiado tiempo en pausa. Tras un mes, los flujos de trabajo técnicos en pausa se detienen de manera incondicional. De forma predeterminada, se activa todos los lunes a las 5 a. m. Para obtener más información, consulte [Gestión de flujos de trabajo en pausa](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Limpieza de solicitud de privacidad** (cleanupPrivacyRequests) | Reglamento de protección de datos de privacidad | Este flujo de trabajo borra los archivos de solicitud de acceso anteriores a 90 días. |
| **Procesamiento de eventos por lotes** (batchEventsProcessing) | Ejecución de mensaje transaccional (Centro de mensajes - Ejecución) | Este flujo de trabajo permite colocar eventos en lote en cola antes de asociarlos con una plantilla de mensaje. |
| **Procesamiento de eventos en tiempo real** (rtEventsProcessing) | Ejecución de mensaje transaccional (Centro de mensajes - Ejecución) | Este flujo de trabajo permite colocar eventos en tiempo real en cola antes de asociarlos con una plantilla de mensaje. |
| **Sincronización de propuestas** (propositionSynch) | Control del motor de oferta con instancia de ejecución | Este flujo de trabajo sincroniza las propuestas entre la instancia de marketing y la instancia de ejecución utilizada para las interacciones. |
| **Recuperación de eventos en la web** (webAnalyticsGetWebEvents) | Conectores de análisis web | Cada hora, este flujo de trabajo descarga segmentos sobre el comportamiento de los usuarios de Internet en un sitio determinado, los integra en la base de datos de Adobe Campaign e inicia el flujo de trabajo de remarketing. |
| **Sistema de informes de acumulados** (reportingAggregates) | Entrega | Este flujo de trabajo actualiza los agregados que se utilizan en los informes. Se activa cada día a la 2 de la mañana de forma predeterminada. |
| **Envío de indicadores y atributos de campañas** (webAnalyticsSendMetrics) | Conectores de análisis web | Este flujo de trabajo permite enviar indicadores de campaña de correo electrónico desde Adobe Campaign a Adobe Experience Cloud Suite a través del conector de Adobe® Analytics. Los indicadores correspondientes son los siguientes: Enviado (iSent), Número total de aperturas (iTotalRecipientOpen), Número total de destinatarios que hicieron clic (iTotalRecipientClick), Errores (iError), Exclusión (opt-out) (iOptOut). |
| **Stock: pedidos y alertas** (stockMgt) | Instalado de forma predeterminada | Este flujo de trabajo inicia el cálculo de stock en las líneas de pedido y administra los umbrales de alertas de advertencia. |
| **Sincronizar aplicaciones móviles de la recopilación de datos de Adobe Experience Platform** (syncWithLaunch) | Se instala de forma predeterminada a partir de la versión 8.5 | Este flujo de trabajo sincroniza automáticamente las propiedades móviles de la recopilación de datos con Adobe Campaign. |
| **Seguimiento** (seguimiento) | Instalado de forma predeterminada | Este flujo de trabajo realiza la recuperación y la consolidación de la información de seguimiento. También garantiza que se recalculen las estadísticas de seguimiento y envío, especialmente las utilizadas por los flujos de trabajo de archivado del Centro de mensajes. De forma predeterminada, se activa una vez cada hora. |
| **Actualizar estado del evento** (updateEventsStatus) | Ejecución de mensaje transaccional (Centro de mensajes - Ejecución) | Este flujo de trabajo permite asignar un estado a un evento. Los estados de eventos son los siguientes:<ul><li>Pendiente: el evento está en cola. Aún no se le ha asociado ninguna plantilla de mensaje.</li><li>Envío pendiente: el evento está en cola, se le ha asociado una plantilla de mensaje y el envío lo está procesando en ese momento.</li><li>Enviado: este estado se copia desde los registros de envío. Significa que el envío se realizó.</li><li>Envío ignorado: este estado se copia desde los registros de envío. Significa que el envío se ha ignorado.</li><li>Error de envío: este estado se copia desde los registros de envío. Significa que el envío ha fallado.</li><li>Evento no cubierto: el evento no se ha podido asociar con una plantilla de mensaje. El evento no se vuelve a procesar.</li></ul> |
| **Actualización para el envío** (deliverabilityUpdate) | Instalado de forma predeterminada | Una vez instalado el paquete de monitorización de la capacidad de entrega (capacidad de entrega por correo electrónico), este flujo de trabajo se ejecuta todas las noches y gestiona las reglas de calificación de correos electrónicos de devolución, así como la lista de dominios y MX. Esto requiere que el puerto HTTPS se abra en la plataforma. |
