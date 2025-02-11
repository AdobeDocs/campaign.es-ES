---
audience: end-user
user-guide-title: Campaign v8
user-guide-description: Documentación del producto para la versión 8 de Adobe Campaign (consola de cliente).
title: Documentación de Adobe Campaign v8
description: Documentación de Campaign versión 8
breadcrumb-title: Documentación de la versión 8 de Campaign
source-git-commit: d50c746d11b6f1bb0b5af0d5ddab5660b99dc359
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 99%

---


# Documentación de Adobe Campaign versión 8 (consola) {#campaign-v8}

+ [Documentación de Campaign versión 8](campaign-home.md)
+ Notas de la versión{#releases}
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
+ Introducción {#new}
   + [Introducción a Adobe Campaign](start/get-started.md)
   + [Funcionalidades clave](start/whats-new.md)
   + [Descubra la nueva interfaz de usuario](start/campaign-ui.md)
   + [Conexión a Campaign](start/connect.md)
   + [Componentes y procesos](start/ac-components.md)
   + [De Campaign Classic v7 a v8](start/v7-to-v8.md)
   + [De Campaign Standard a v8](start/acs-to-v8.md)
   + [Preguntas frecuentes](start/campaign-faq.md)
+ Campaign Management {#campaigns}
   + [Introducción a las campañas](start/campaigns.md)
   + [Orquestación de campañas >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=es)
+ Envío de mensajes{#send}
   + [Introducción a los mensajes](start/gs-message.md)
   + [Creación de su primer envío](start/create-message.md)
   + [Prácticas recomendadas de envíos](start/delivery-best-practices.md)
   + Correos electrónicos {#emails}
      + [Diseño y validación de correos electrónicos](send/email.md)
      + [Vínculo a la página espejo](send/mirror-page.md)
      + [Añadir una dirección CCO](send/email-bcc.md)
      + [Definir los parámetros de correo electrónico adicionales](send/email-parameters.md)
      + [Envío y monitorización de correos electrónicos](send/send.md)
   + SMS {#sms}
      + [Introducción a los SMS](send/sms/sms.md)
      + Configurar el canal SMS {#config-sms}
         + [Configuración de envío de SMS](send/sms/sms-delivery-settings.md)
         + [Configuración de cuenta externa de SMPP](send/sms/smpp-external-account.md)
         + [Características del canal SMS](send/sms/sms-channel.md)
         + [Validación de una conexión SMPP](send/sms/smpp-connection.md)
         + [Instancia independiente](send/sms/sms-standalone-instance.md)
         + [Infraestructura intermediaria](send/sms/sms-mid-sourcing.md)
         + [Descripción del conector SMPP](send/sms/smpp-connector-delivery.md)
      + Creación de un SMS {#create-sms}
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
   + [Mensajería LINE](send/line.md)
   + [Correo directo](send/direct-mail.md)
   + [X (Twitter)](send/twitter.md)
   + Personalización del contenido {#personalize}
      + [Introducción a la personalización](send/personalize.md)
      + [Datos de personalización](send/personalization-data.md)
      + [Añadir campos de personalización](send/personalization-fields.md)
      + [Utilizar bloques de personalización](send/personalization-blocks.md)
      + [Crear condiciones](send/conditions.md)
   + Validación y envío de la entrega{#validate}
      + [Previsualización y pruebas](send/preview-and-proof.md)
      + [Análisis de envíos](send/delivery-analysis.md)
      + [Configuración y envío de la entrega](send/configure-and-send.md)
      + [Optimización del tiempo de envío](send/predictive.md)
   + Errores, rechazos y cuarentenas{#failures}
      + [Cuarentenas](send/quarantines.md)
      + [Errores de envío](send/delivery-failures.md)
   + [Trabajo con plantillas de envío](send/create-templates.md)
   + Mensajes transaccionales{#real-time}
      + [Introducción a los mensajes transaccionales](send/transactional.md)
      + [Creación y publicación de una plantilla](send/transactional-template.md)
      + Administración de eventos {#event}
         + [Recopilación y procesamiento de eventos](send/event-processing.md)
         + [Comprensión de la descripción del evento](send/event-description.md)
         + [Mensajes de envío y monitorización](send/delivery-execution.md)
+ Gestión de perfiles y públicos {#audience}
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
   + Creación de públicos {#create-audiences}
      + [Creación de una lista de contactos](audiences/create-audiences.md)
      + [Creación y administración de filtros](audiences/create-filters.md)
      + [Compartir públicos con soluciones de Adobe](start/shared-audiences.md)
   + [Prácticas recomendadas](audiences/audiences-best-practices.md)
   + [Administración de suscripciones](start/subscriptions.md)
+ Gestión de contenidos {#content}
   + [Creación de páginas de aterrizaje](dev/landing-pages.md)
   + [Diseño de aplicaciones y formularios web](dev/webapps.md)
+ Automatización y flujos de trabajo{#automation}
   + [Guía de automatización de Campaign >](https://experienceleague.adobe.com/es/docs/campaign/automation/home)
+ Administración de seguridad y privacidad {#privacy}
   + [Administración de solicitudes de privacidad](start/privacy.md)
   + [Directrices de seguridad](config/security.md)
   + [Complemento de seguridad mejorada](config/enhanced-security.md)
+ Gestión de decisiones {#offers}
   + [Introducción a la interacción en tiempo real](interaction/interaction.md)
   + [Entornos y arquitectura](interaction/interaction-architecture.md)
   + [Prácticas recomendadas](interaction/interaction-best-practices.md)
   + Definir la configuración de {#interaction-settings}
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
   + [Introducción a los flujos de trabajo](config/workflows.md)
   + [Importación de datos](start/import.md)
   + [Documentación del flujo de trabajo](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=es)
+ Integraciones {#connect}
   + [Conectar Campaign con otras soluciones](connect/integration.md)
   + Campaign + Experience Platform{#ac-aep}
      + [Compartir y sincronizar públicos y atributos de perfil](connect/ac-aep.md)
      + [Actualización de perfiles de AEP desde las páginas de aterrizaje de Campaign](connect/ac-aep-landing-pages.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Activadores de Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Workfront](connect/ac-workfront.md)
   + [Campaign + X (Twitter)](connect/ac-tw.md)
   + [Campaign + Base de datos externa](connect/fda.md)
   + Campaign + su CRM{#ac-crm}
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
+ Arquitectura y configuración {#config}
   + Arquitectura de la versión 8 de Campaign{#architecture}
      + [Principios globales](architecture/general-architecture.md)
      + [Modelos de arquitectura](architecture/architecture.md)
      + [Implementación de FDA de Campaign](architecture/fda-deployment.md)
      + Implementación empresarial (FDAC) {#ffda}
         + [¿Qué es el FDAC de Campaign?](architecture/enterprise-deployment.md)
         + [Administración de claves y unicidad](architecture/keys.md)
         + [Nuevas API](architecture/new-apis.md)
         + [Mecanismo de ensayo de API](architecture/staging.md)
         + [Mecanismo de replicación](architecture/replication.md)
   + Implementación {#implement}
      + [Pasos de implementación](start/implement.md)
      + [Personalizar la instancia](dev/customize.md)
      + [Prácticas recomendadas del modelo de datos](dev/datamodel-best-practices.md)
   + Configuración {#configuration}
      + [Configuración de la interfaz de usuario](config/ui-settings.md)
      + [Administrar carpetas y vistas](audiences/folders-and-views.md)
      + [Configuración de mensajería transaccional](config/transactional-msg-settings.md)
      + [Integración de los SDK de Campaign con la aplicación - PÁGINA OBSOLETA](config/push-config.md)
      + [Cuentas externas](config/external-accounts.md)
+ Recursos para desarrolladores {#developer}
   + [Modelo de datos de Campaign](dev/datamodel.md)
   + Esquemas y formularios {#shemas-forms}
      + [Usar esquemas](dev/schemas.md)
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
+ [Notas técnicas de Campaign >](https://experienceleague.adobe.com/es/docs/campaign/technotes-ac/technotes-home)
+ [Documentación de la interfaz de usuario web de Campaign >](https://experienceleague.adobe.com/es/docs/campaign-web/v8/campaign-web-home)

