---
audience: user
user-guide-title: Guía de automatización de Campaign
user-guide-description: Guía de automatización de Campaign
feature: Overview
source-git-commit: 00d9c3229b7bbabfec3b1750ae84978545fdc218
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 84%

---


# Guías de automatización de Campaign {#automation}

+ [Guía de automatización de Campaign](home.md)
+ Automatización con flujos de trabajo {#workflows}
   + Introducción a los flujos de trabajo {#introduction}
      + [Acerca de los flujos de trabajo](workflow/about-workflows.md)
      + Tipos de flujos de trabajo {#wf-type}
         + [Flujos de trabajo de segmentación](workflow/targeting-workflows.md)
         + [Flujos de trabajo de la campaña](workflow/campaign-workflows.md)
         + [Flujos de trabajo técnicos](workflow/technical-workflows.md)
      + [Creación de un flujo de trabajo](workflow/build-a-workflow.md)
      + [Prácticas recomendadas](workflow/workflow-best-practices.md)
      + [Uso de datos de flujo de trabajo](workflow/use-workflow-data.md)
   + Ejecución de un flujo de trabajo  {#executing-a-workflow}
      + [Inicio de un flujo de trabajo](workflow/start-a-workflow.md)
      + [Ciclo de vida del flujo de trabajo](workflow/workflow-life-cycle.md)
      + [Configuración de aprobaciones](workflow/define-approvals.md)
   + Monitorización de flujos de trabajo {#monitoring-workflows}
      + [Monitorización de la ejecución del flujo de trabajo](workflow/monitor-workflow-execution.md)
      + [Monitorización de flujos de trabajo técnicos](workflow/monitor-technical-workflows.md)
      + [Mapa de calor del flujo de trabajo](workflow/heatmap.md)
   + Actividades de flujo de trabajo {#wf-activities}
      + [Introducción a las actividades](workflow/activities.md)
      + Actividades de segmentación {#targeting-activities}
         + [Lista de actividades de segmentación](workflow/targeting-activities.md)
         + [Celdas](workflow/cells.md)
         + [Cambio de la fuente de datos](workflow/change-data-source.md)
         + [Cambio de dimensión](workflow/change-dimension.md)
         + [Conector CRM](workflow/crm-connector.md)
         + [Deduplicación](workflow/deduplication.md)
         + [Descripción del envío](workflow/delivery-outline.md)
         + [Editar esquema](workflow/edit-schema.md)
         + [Enriquecimiento &#x200B;](workflow/enrichment.md)
         + [Exclusión &#x200B;](workflow/exclusion.md)
         + [Consulta incremental](workflow/incremental-query.md)
         + [Intersección](workflow/intersection.md)
         + [Actualización de listas](workflow/list-update.md)
         + [Ofertas por celda](workflow/offers-by-cell.md)
         + [Motor de oferta](workflow/offer-engine.md)
         + [Consulta](workflow/query.md)
         + [Lista de lectura](workflow/read-list.md)
         + [División](workflow/split.md)
         + [Servicios de suscripción](workflow/subscription-services.md)
         + [Unión](workflow/union.md)
         + [Actualización de datos](workflow/update-data.md)
      + Actividades de control de flujo {#flow-control-activities}
         + [Lista de actividades de control de flujo](workflow/flow-control-activities.md)
         + [Alerta](workflow/alert.md)
         + [Combinación-Y](workflow/and-join.md)
         + [Aprobación](workflow/approval.md)
         + [Señal externa](workflow/external-signal.md)
         + [Bifurcación](workflow/fork.md)
         + [Saltos (puntos iniciales y finales)](workflow/jump-start-point-and-end-point.md)
         + [Inicio y final](workflow/start-and-end.md)
         + [Planificador](workflow/scheduler.md)
         + [Subflujo de trabajo](workflow/sub-workflow.md)
         + [Prueba](workflow/test.md)
         + [Restricción de tiempo](workflow/time-constraint.md)
         + [Esperar](workflow/wait.md)
      + Actividades de acción {#action-activities}
         + [Lista de actividades de acción](workflow/action-activities.md)
         + [Administración de contenido](workflow/content-management.md)
         + [Envío continuo](workflow/continuous-delivery.md)
         + [Envíos en canales múltiples](workflow/cross-channel-deliveries.md)
         + [Extracción de datos (archivo)](workflow/extraction-file.md)
         + [Carga de datos (archivo)](workflow/data-loading-file.md)
         + [Carga de datos (RDBMS)](workflow/data-loading-rdbms.md)
         + [Envío](workflow/delivery.md)
         + [Control de envíos](workflow/delivery-control.md)
         + [Aprobación local](workflow/local-approval.md)
         + [Carga (SOAP)](workflow/loading-soap.md)
         + [Módulo Nlserver](workflow/nlserver-module.md)
         + [Envío recurrente](workflow/recurring-delivery.md)
         + [Código SQL y código JavaScript](workflow/sql-code-and-javascript-code.md)
         + [Administración de datos SQL](workflow/sql-data-management.md)
         + [Actualización del agregado](workflow/update-aggregate.md)
      + Actividades de evento {#event-activities}
         + [Lista de actividades de evento](workflow/event-activities.md)
         + [Recolector de ficheros](workflow/file-collector.md)
         + [Transferencia de archivos](workflow/file-transfer.md)
         + [Correos electrónicos entrantes](workflow/inbound-emails.md)
         + [SMS entrantes](workflow/inbound-sms.md)
         + [Descarga web](workflow/web-download.md)
   + Casos de uso {#use-cases}
      + [Acerca de los casos de uso de flujos de trabajo](workflow/workflow-use-cases.md)
      + Envíos {#deliveries}
         + [Uso de la actividad de aprobación local](workflow/local-approval-activity.md)
         + [Envío de un correo electrónico de cumpleaños](workflow/send-a-birthday-email.md)
         + [Carga de contenido de envíos](workflow/load-delivery-content.md)
         + [Flujo de trabajo de envíos en canales múltiples](workflow/cross-channel-delivery-workflow.md)
         + [Enriquecimiento de correo electrónico con campos de datos personalizados](workflow/email-enrichment-with-custom-date-fields.md)
      + Monitorización {#monitoring}
         + [Envío de un informe a una lista](workflow/send-a-report-to-a-list.md)
         + [Supervisión de los flujos de trabajo](workflow/workflow-supervision.md)
         + [Envío de alertas personalizadas a operadores](workflow/send-alerts-to-operators.md)
      + Administración de datos {#data-management}
         + [Coordinación de actualizaciones de datos](workflow/coordinate-data-updates.md)
         + [Creación de una lista de resumen](workflow/create-a-summary-list.md)
         + [Enriquecimiento de datos](workflow/enrich-data.md)
         + [Uso de agregados](workflow/using-aggregates.md)
         + [Uso de la funcionalidad de combinación de la actividad de anulación de duplicación](workflow/deduplication-merge.md)
         + [Configuración de un flujo de trabajo de importación recurrente](workflow/recurring-import-workflow.md)
      + Diseño de consultas {#designing-queries}
         + [Actualización de lista trimestral con una consulta incremental](workflow/quarterly-list-update.md)
      + Consulta y filtro  {#designing-queries}
         + [Consulta de la tabla de destinatarios](workflow/querying-recipient-table.md)
         + [Consulta de la información de envío](workflow/query-delivery-info.md)
         + [Calcular agregados](workflow/compute-aggregates.md)
         + [Realización de consultas mediante la administración de agrupación](workflow/query-grouping-management.md)
         + [Realización de consultas con una relación de varios a varios](workflow/query-many-to-many-relationship.md)
         + [Adición de un campo calculado de tipo Enumeración](workflow/adding-enumeration-type-calculated-field.md)
         + [Creación de un filtro](workflow/create-a-filter.md)
         + [Filtro de destinatarios duplicados](workflow/filter-duplicated-recipients.md)
   + Configuración avanzada {#advanced-management}
      + [Propiedades del flujo de trabajo](workflow/workflow-properties.md)
      + [Parámetros avanzados](workflow/advanced-parameters.md)
      + [Plantillas y scripts de JavaScript](workflow/javascript-scripts-and-templates.md)
      + [Ejemplos de código JavaScript en flujos de trabajo](workflow/javascript-in-workflows.md)
      + [Acceso a una base de datos externa](workflow/accessing-an-external-database-fda.md)
      + [Administración de permisos](workflow/managing-rights.md)
      + [Cambio de imágenes de actividad](workflow/change-activity-images.md)
      + [Administrar zonas horarias](workflow/managing-time-zones.md)
+ Orquestación de campañas  {#campaign-orchestration}
   + [Introducción a las campañas de marketing](campaigns/set-up-campaigns.md)
   + [Creación de programas y campañas](campaigns/marketing-campaign-create.md)
   + [Creación y configuración de plantillas](campaigns/marketing-campaign-templates.md)
   + [Agregar envíos](campaigns/marketing-campaign-deliveries.md)
   + [Selección del público](campaigns/marketing-campaign-target.md)
   + [Administración de documentos y recursos](campaigns/marketing-campaign-assets.md)
   + [Configuración y administración de aprobaciones](campaigns/marketing-campaign-approval.md)
   + [Campañas recurrentes y periódicas](campaigns/recurring-periodic-campaigns.md)
   + [Monitorización de campañas](campaigns/marketing-campaign-monitoring.md)
   + [Proveedores, stock y presupuestos](campaigns/providers-stocks-and-budgets.md)
+ Optimización de la campaña (complemento){#campaign-optimization}
   + [Introducción a las tipologías de campaña](campaign-opt/campaign-typologies.md)
   + [Reglas de filtrado](campaign-opt/filtering-rules.md)
   + [Reglas de control](campaign-opt/control-rules.md)
   + [Reglas de presión](campaign-opt/pressure-rules.md)
   + [Reglas de coherencia](campaign-opt/consistency-rules.md)
   + [Aplicación de reglas](campaign-opt/apply-rules.md)
   + [Simulaciones en Campaign](campaign-opt/campaign-simulations.md)
+ Administración de recursos de marketing (complemento){#mrm}
   + [Introducción a la administración de recursos de marketing](mrm/about-marketing-resource-management.md)
   + [Creación y administración de tareas](mrm/creating-and-managing-tasks.md)
   + [Costes de control](mrm/controlling-costs.md)
   + [Administración de recursos de marketing](mrm/managing-marketing-resources.md)
   + [Foros de debate](mrm/discussion-forums.md)
+ Marketing distribuido (complemento) {#distributed-marketing}
   + [Introducción al marketing distribuido](distributed-marketing/about-distributed-marketing.md)
   + [Creación de una campaña local](distributed-marketing/creating-a-local-campaign.md)
   + [Creación de una campaña colaborativa](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Publicación del paquete de campaña](distributed-marketing/publishing-the-campaign-package.md)
   + [Acceso a campañas](distributed-marketing/accessing-campaigns.md)
   + [Seguimiento de una campaña](distributed-marketing/tracking-a-campaign.md)
   + [Casos de uso](distributed-marketing/examples.md)
+ [&lt; Volver a la documentación de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/campaign-home)
