---
audience: end-user
user-guide-title: Campaign v8
user-guide-description: Documentación del producto para la versión 8 de Adobe Campaign (consola de cliente).
title: Documentación de Adobe Campaign v8
description: Documentación de Campaign versión 8
breadcrumb-title: Documentación de la versión 8 de Campaign
source-git-commit: 449f24cb23afa2d6bd7d6f2ad7ff3ba65e0a1d5d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 96%

---


# Documentación de Adobe Campaign versión 8 (consola) {#campaign-v8}

+ [Documentación de Campaign versión 8](campaign-home.md)
+ Notas de la versión {#releases}
   + [Notas de la versión preliminar](start/e-release-notes.md)
   + [Versiones y actualizaciones](start/upgrades.md)
   + [Últimas versiones](start/release-notes.md)
   + Versiones anteriores {#previous-rn}
      + [2025](start/release-notes-2025.md)
      + [2024](start/release-notes-2024.md)
      + [2023](start/release-notes-2023.md)
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Mecanismos de protección](start/ac-guardrails.md)
   + [Problemas conocidos](start/known-issues.md)
   + [Matriz de compatibilidad](start/compatibility-matrix.md)
   + [Actualizaciones de la documentación](start/documentation-updates.md)
+ Introducción  {#new}
   + [Introducción a Adobe Campaign](start/get-started.md)
   + [Funcionalidades clave](start/whats-new.md)
   + [Descubrimiento de la interfaz de usuario](start/campaign-ui.md)
   + [Conexión a Campaign](start/connect.md)
   + [Componentes y procesos](start/ac-components.md)
   + [De Campaign Classic v7 a v8](start/v7-to-v8.md)
   + [De Campaign Standard a v8](start/acs-to-v8.md)
   + [Preguntas frecuentes](start/campaign-faq.md)
+ Administración de campañas {#campaigns}
   + [Introducción a las campañas](start/campaigns.md)
   + [Orquestación de campañas >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=es)
+ Envío de mensajes{#send}
   + [Introducción a los mensajes](start/gs-message.md)
   + [Creación de su primer envío](start/create-message.md)
   + [Trabajo con plantillas de envío](send/create-templates.md)
   + [Prácticas recomendadas para envíos](start/delivery-best-practices.md)
   + Correos electrónicos {#emails}
      + [Diseño y validación de correos electrónicos](send/email.md)
      + [Definición del contenido del correo electrónico](send/defining-the-email-content.md)
      + [Definición del contenido interactivo](send/defining-interactive-content.md)
      + [Vínculo a la página espejo](send/mirror-page.md)
      + [Añadir una dirección CCO](send/email-bcc.md)
      + [Definir los parámetros de correo electrónico adicionales](send/email-parameters.md)
      + [Envío y monitorización de correos electrónicos](send/send.md)
      + [Envío de correos electrónicos en móviles japoneses](send/sending-emails-on-japanese-mobiles.md)
      + [Adjuntar archivos a un correo electrónico](send/attaching-files.md)
   + SMS {#sms}
      + [Introducción a los SMS](send/sms/sms.md)
      + Configuración del canal de SMS {#config-sms}
         + [Configuración de envío de SMS](send/sms/sms-delivery-settings.md)
         + [Configuración de cuenta externa de SMPP](send/sms/smpp-external-account.md)
         + [Características del canal SMS](send/sms/sms-channel.md)
         + [Validación de una conexión SMPP](send/sms/smpp-connection.md)
         + [Instancia independiente](send/sms/sms-standalone-instance.md)
         + [Infraestructura intermediaria](send/sms/sms-mid-sourcing.md)
         + [Descripción del conector SMPP](send/sms/smpp-connector-delivery.md)
      + Creación de un SMS  {#create-sms}
         + [Creación de un envío de SMS](send/sms/create-sms.md)
         + [Definición del contenido](send/sms/sms-content.md)
         + [Selección del público](send/sms/sms-audience.md)
      + Validación y envío de SMS {#validate-sms}
         + [Envío de pruebas SMS](send/sms/sms-proofs.md)
         + [Envío al público](send/sms/sms-send.md)
      + [Monitorización y seguimiento de SMS](send/sms/sms-monitor.md)
   + Notificaciones push {#push}
      + [Creación y envío de notificaciones push](send/push.md)
      + Push enriquecido {#rich-push}
         + [Diseño de un envío push enriquecido para Android](send/rich-push-android.md)
         + [Diseño de un envío push enriquecido para iOS](send/rich-push-ios.md)
      + [Configuración de canal de notificaciones push](send/push-settings.md)
      + [Configuración de sus notificaciones push con la recopilación de datos](send/push-data-collection.md)
   + [Mensajería LINE](send/line/line.md)
   + [Correo directo](send/direct-mail.md)
   + [X (Twitter)](send/twitter.md)
   + [Canal externo personalizado](send/custom-channel.md)
   + Personalización del contenido {#personalize}
      + [Introducción a la personalización](send/personalize.md)
      + [Datos de personalización](send/personalization-data.md)
      + [Añadir campos de personalización](send/personalization-fields.md)
      + [Utilizar bloques de personalización](send/personalization-blocks.md)
      + [Crear condiciones](send/conditions.md)
   + Validación y envío de la entrega {#validate}
      + [Previsualización y pruebas](send/preview-and-proof.md)
      + [Análisis de envíos](send/delivery-analysis.md)
      + [Configuración y envío de la entrega](send/configure-and-send.md)
      + [Optimización del tiempo de envío](send/predictive.md)
   + Errores, rechazos y cuarentenas {#failures}
      + [Cuarentena](send/quarantines.md)
      + [Errores de envío](send/delivery-failures.md)
   + Administración de la entregabilidad {#deliverability-management}
      + [¿Qué es la entregabilidad?](send/about-deliverability.md)
      + [Contenido de mensajes de control](send/control-message-content.md)
      + [Supervisión de la entregabilidad](send/monitoring-deliverability.md)
      + [Procesamiento de la bandeja de entrada](send/inbox-rendering.md)
      + [SpamAssassin](send/spamassassin.md)
   + Mensajes transaccionales {#real-time}
      + [Introducción a los mensajes transaccionales](send/transactional.md)
      + [Creación y publicación de una plantilla](send/transactional-template.md)
      + Administración de eventos  {#event}
         + [Recopilación y procesamiento de eventos](send/event-processing.md)
         + [Comprensión de la descripción del evento](send/event-description.md)
         + [Mensajes de envío y monitorización](send/delivery-execution.md)
+ Gestión de públicos y perfiles {#audience}
   + [Introducción a perfiles y públicos](audiences/gs-audiences.md)
   + [Trabajo con públicos](start/audiences.md)
   + [Acceso a perfiles](audiences/view-profiles.md)
   + Adición de perfiles {#add-profiles}
      + [Creación de perfiles manual](audiences/create-profiles.md)
      + [Importación de perfiles de un archivo](audiences/import-profiles.md)
      + [Trabajo con perfiles externos](audiences/external-profiles.md)
      + [Recopilación de datos de perfil en formularios web](audiences/collect-profiles.md)
      + [Trabajar con asignaciones de destino](audiences/target-mappings.md)
      + [Crear perfiles de prueba](audiences/test-profiles.md)
   + Crear públicos {#create-audiences}
      + [Creación de una lista de contactos](audiences/create-audiences.md)
      + [Creación y administración de filtros](audiences/create-filters.md)
      + [Compartir públicos con soluciones de Adobe](start/shared-audiences.md)
   + [Prácticas recomendadas](audiences/audiences-best-practices.md)
   + [Administración de suscripciones](start/subscriptions.md)
+ Administración de contenido {#content}
   + [Creación de páginas de aterrizaje](dev/landing-pages.md)
   + [Diseño de aplicaciones y formularios web](dev/webapps.md)
+ Flujos de trabajo {#workflows}
   + [Introducción a los flujos de trabajo](config/workflows.md)
   + [Documentación de flujo de trabajo >](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es)
+ Administración de la privacidad y la seguridad {#privacy}
   + [Administración de solicitudes de privacidad](start/privacy.md)
   + [Directrices de seguridad](config/security.md)
   + [Complemento de seguridad mejorada](config/enhanced-security.md)
+ Gestión de decisiones {#offers}
   + [Introducción a la interacción en tiempo real](interaction/interaction.md)
   + [Entornos y arquitectura](interaction/interaction-architecture.md)
   + [Prácticas recomendadas](interaction/interaction-best-practices.md)
   + Definición de la configuración {#interaction-settings}
      + [Creación de operadores](interaction/interaction-operators.md)
      + [Creación de entornos](interaction/interaction-env.md)
      + [Creación de filtros predefinidos](interaction/interaction-predefined-filters.md)
      + [Creación de espacios de oferta](interaction/interaction-offer-spaces.md)
   + [Creación de un catálogo de ofertas](interaction/interaction-offer-catalog.md)
   + [Creación de una oferta](interaction/interaction-offer.md)
   + [Enviar una oferta (de salida)](interaction/interaction-send-offers.md)
   + Presentación de una oferta (entrante){#inbound}
      + [Contexto](interaction/interaction-present-offers.md)
      + [Invocación de una oferta en una página web](interaction/interaction-integration.md)
      + [Administración de interacciones anónimas](interaction/anonymous-interactions.md)
   + [Informes e historial](interaction/interaction-tracking.md)
   + [Casos de uso](interaction/interaction-use-cases.md)
+ Creación de informes y análisis {#analytics}
   + [Seguimiento y monitorización](start/tracking.md)
   + [Pista de auditoría](reporting/audit-trail.md)
   + Trabajo con informes{#reports}
      + [Introducción a los informes](reporting/gs-reporting.md)
      + Crear cubos{#cubes}
         + [Introducción a los cubos](reporting/gs-cubes.md)
         + [Crear un cubo](reporting/cube-indicators.md)
         + [Uso de cubos para crear informes](reporting/cube-tables.md)
         + [Personalizar sus cubos](reporting/customize-cubes.md)
      + Informes integrados{#ac-reports}
         + [Lista de informes integrados](reporting/built-in-reports.md)
         + [Informes globales](reporting/global-reports.md)
         + [Informes de envío](reporting/delivery-reports.md)
         + [Cálculo de métricas integradas](reporting/metrics-calculation.md)
      + [Informes personalizados](reporting/custom-reports.md)
+ Administración de datos {#data}
   + Consultar la base de datos {#query}
      + [Trabajo con el editor de consultas](start/query-editor.md)
      + [Diseño de consultas](start/design-queries.md)
      + [Definición de condiciones de filtro](start/filter-conditions.md)
   + [Importación de datos](start/import.md)
   + [Documentación de flujo de trabajo >](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es)
+ Integraciones {#connect}
   + [Conectar Campaign con otras soluciones](connect/integration.md)
   + Campaign + Experience Platform {#ac-aep}
      + [Compartir y sincronizar públicos y atributos de perfil](connect/ac-aep.md)
      + [Actualización de perfiles de AEP desde las páginas de destino de Campaign](connect/ac-aep-landing-pages.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Activadores de Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Workfront](connect/ac-workfront.md)
   + [Campaign + X (Twitter)](connect/ac-tw.md)
   + [Campaign + Base de datos externa](connect/fda.md)
   + Campaign + su CRM  {#ac-crm}
      + [Introducción a los conectores CRM](connect/crm.md)
      + [Trabajo con Campaign y SFDC](connect/ac-sfdc.md)
      + [Trabajo con Campaign y Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Sincronizar datos](connect/crm-data-sync.md)
+ Administración {#admin}
   + Usuarios y permisos {#permissions}
      + [Introducción a los permisos](start/gs-permissions.md)
      + [Administrar permisos de usuario](start/manage-permissions.md)
      + [Agregar permisos en carpetas](start/folder-permissions.md)
   + [Panel de control](config/self-service.md)
+ Arquitectura {#architecture}
   + [Principios globales](architecture/general-architecture.md)
   + [Modelos de arquitectura](architecture/architecture.md)
   + [Implementación de FDA de Campaign](architecture/fda-deployment.md)
   + Implementación empresarial (FDAC) {#ffda}
      + [¿Qué es el FDAC de Campaign?](architecture/enterprise-deployment.md)
      + [Administración de claves y unicidad](architecture/keys.md)
      + [Nuevas API](architecture/new-apis.md)
      + [Mecanismo de ensayo de API](architecture/staging.md)
      + [Mecanismo de replicación](architecture/replication.md)
+ Configuración {#config}
   + Implementación {#implement}
      + [Pasos de implementación](start/implement.md)
      + [Personalizar la instancia](dev/customize.md)
      + [Prácticas recomendadas del modelo de datos](dev/datamodel-best-practices.md)
   + Configuración {#settings}
      + [Configuración de la interfaz de usuario](config/ui-settings.md)
      + [Administrar carpetas y vistas](audiences/folders-and-views.md)
      + [Trabajo con enumeraciones](config/enumerations.md)
      + [Configuración de mensajería transaccional](config/transactional-msg-settings.md)
      + [Integración de los SDK de Campaign con la aplicación - PÁGINA OBSOLETA](config/push-config.md)
      + [Cuentas externas](config/external-accounts.md)
+ Recursos para desarrolladores {#developer}
   + [Modelo de datos de Campaign](dev/datamodel.md)
   + Esquemas y formularios {#shemas-forms}
      + [Trabajo con esquemas](dev/schemas.md)
      + [Crear esquemas](dev/create-schema.md)
      + [Ampliar esquemas](dev/extend-schema.md)
      + [Filtrar esquemas](dev/filter-schema.md)
      + [Estructura del esquema](dev/schema-structure.md)
      + [Asignación de base de datos](dev/database-mapping.md)
      + [Administración de claves](dev/database-keys.md)
      + [Administración de vínculos](dev/database-links.md)
      + [Restringir la vista IP](dev/restrict-pi-view.md)
      + [Usar una tabla de destinatarios personalizada](dev/custom-recipient.md)
      + [Actualizar la base de datos](dev/update-database-structure.md)
      + [Formularios de entrada](dev/forms.md)
   + [Trabajo con paquetes de datos](dev/packages.md)
   + [API de Campaign](dev/api.md)
   + API de REST {#apis}
      + [Introducción a las API de REST](dev/api/get-started-apis.md)
      + [Recomendaciones y limitaciones](dev/api/limitations.md)
      + [Razones para utilizar las API de REST](dev/api/why-using-campaign-standard-apis.md)
      + [Configuración del acceso a API](dev/api/setting-up-api-access.md)
      + Conceptos globales {#global-concepts}
         + [Lectura obligatoria](dev/api/must-read.md)
         + [Puntos de conexión](dev/api/endpoints.md)
         + [Mecanismo de metadatos](dev/api/metadata-mechanism.md)
         + [Verbos](dev/api/verbs.md)
         + [Operaciones adicionales](dev/api/sorting.md)
         + [Recursos personalizados](dev/api/custom-resources.md)
      + [Uso de recursos personalizados](dev/api/interacting-with-custom-resources.md)
      + Administración de perfiles {#managing-profiles}
         + [Recuperación de perfiles](dev/api/retrieving-profiles.md)
         + [Actualización de perfiles](dev/api/updating-profiles.md)
         + [Creación de perfiles](dev/api/creating-profiles-api.md)
      + Administración de servicios y suscripciones {#managing-services-and-subscriptiopns}
         + [Creación de un servicio](dev/api/creating-a-service.md)
         + [Recuperación de suscripciones](dev/api/retrieving-subscriptions.md)
         + [Realización de suscripciones](dev/api/perform-subscriptions.md)
         + [Eliminación de suscripciones](dev/api/deleting-subscriptions.md)
      + [Administración de mensajes transaccionales](dev/api/managing-transactional-messages.md)
      + Administración de flujos de trabajo {#managing-workflows}
         + [Control de un flujo de trabajo](dev/api/controlling-a-workflow.md)
         + [Activación de una actividad de señal](dev/api/triggering-a-signal-activity.md)
+ [Notas técnicas de Campaign >](https://experienceleague.adobe.com/es/docs/campaign/technotes-ac/technotes-home)
+ [Documentación de la interfaz de usuario web de Campaign >](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home)

