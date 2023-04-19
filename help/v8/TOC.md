---
audience: end-user
user-guide-title: Campaign v8
description: Documentación de la versión 8 de Campaign
breadcrumb-title: Información general de Campaign
title: Documentos de la versión 8 de Campaign
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 94%

---


# Documentación de Adobe Campaign v8 {#campaign-v8}

+ [Documentación de la versión 8 de Campaign](campaign-home.md)
+ Versiones y actualizaciones más recientes {#releases}
   + [Notas de la versión preliminar](start/e-release-notes.md)
   + [Notas de la versión ](start/release-notes.md)
   + Notas de la versión anterior {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Mecanismos de protección](start/ac-guardrails.md)
   + [Problemas conocidos](start/known-issues.md)
   + [Matriz de compatibilidad](start/compatibility-matrix.md)
+ Introducción {#new}
   + [Introducción a Adobe Campaign](start/get-started.md)
   + [Funcionalidades clave](start/whats-new.md)
   + [Componentes y procesos](start/ac-components.md)
   + [Conéctese a Campaign](start/connect.md)
   + IU de Campaign {#ac-ui}
      + [Descubrimiento de la interfaz de Campaign](start/campaign-ui.md)
      + [Personalización de la interfaz de Campaign](start/customize-ui.md)
      + [Administrar carpetas y vistas](audiences/folders-and-views.md)
   + [De la versión 7 a la 8 de Classic](start/v7-to-v8.md)
   + [Preguntas frecuentes](start/campaign-faq.md)
+ Campaign Management {#campaigns}
   + [Introducción a las campañas](start/campaigns.md)
   + [Orquestación de campañas >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=es)
   + Envío de mensajes{#send}
      + [Introducción a los mensajes](start/create-message.md)
      + [Trabajo con plantillas de envío](send/create-templates.md)
      + Correos electrónicos {#emails}
         + [Diseño y validación de correos electrónicos](send/email.md)
         + [Vínculo a la página espejo](send/mirror-page.md)
         + [Envío y monitorización de correos electrónicos](send/send.md)
      + [SMS](send/sms.md)
      + [Notificaciones push](send/push.md)
      + [Mensajería LINE](send/line.md)
      + [Correo directo](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + Mensajes transaccionales {#real-time}
         + [Introducción a los mensajes transaccionales](send/transactional.md)
         + [Creación y publicación de una plantilla](send/transactional-template.md)
         + Gestión de eventos {#event}
         + [Recopilar y procesar eventos](send/event-processing.md)
         + [Explicación de la descripción del evento](send/event-description.md)
         + [Envío y monitorización de mensajes](send/delivery-execution.md)
      + Errores, rechazos y cuarentenas{#failures}
         + [Cuarentenas](send/quarantines.md)
         + [Errores de envío](send/delivery-failures.md)
      + [Optimización del tiempo de envío](send/predictive.md)
      + [Administración de suscripciones](start/subscriptions.md)
      + Personalización del contenido {#personalize}
         + [Introducción a la personalización](send/personalize.md)
         + [Datos de personalización](send/personalization-data.md)
         + [Añadir campos de personalización](send/personalization-fields.md)
         + [Utilizar bloques de personalización](send/personalization-blocks.md)
         + [Crear condiciones](send/conditions.md)
      + Validación del envío {#validate}
         + [Previsualización y pruebas](send/preview-and-proof.md)
         + [Análisis de envíos](send/delivery-analysis.md)
+ Gestión de perfiles y audiencias {#audience}
   + [Introducción a perfiles y audiencias](audiences/gs-audiences.md)
   + [Trabajo con audiencias](start/audiences.md)
   + [Acceso a perfiles](audiences/view-profiles.md)
   + Adición de perfiles {#add-profiles}
      + [Creación de perfiles manual](audiences/create-profiles.md)
      + [Importación de perfiles de un archivo](audiences/import-profiles.md)
      + [Trabajo con perfiles externos](audiences/external-profiles.md)
      + [Recopilación de datos de perfil en formularios web](audiences/collect-profiles.md)
      + [Trabajar con asignaciones de destino](audiences/target-mappings.md)
   + Creación de audiencias {#create-audiences}
      + [Creación de una lista de contactos](audiences/create-audiences.md)
      + [Creación y administración de filtros](audiences/create-filters.md)
   + [Compartir audiencias con soluciones de Adobe](start/shared-audiences.md)
   + [Prácticas recomendadas](audiences/audiences-best-practices.md)
+ Gestión de contenidos {#content}
   + [Diseño de aplicaciones y formularios web](dev/webapps.md)
+ Administración de seguridad y privacidad {#privacy}
   + [Administración de solicitudes de privacidad](start/privacy.md)
   + [Directrices de seguridad](config/security.md)
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
   + [Enviar una oferta  (saliente)](interaction/interaction-send-offers.md)
   + Presentación de una oferta (entrante){#inbound}
      + [Contexto](interaction/interaction-present-offers.md)
      + [Invocación de una oferta en una página web](interaction/interaction-integration.md)
      + [Administración de interacciones anónimas](interaction/anonymous-interactions.md)
   + [Informes e historial](interaction/interaction-tracking.md)
   + [Casos de uso](interaction/interaction-use-cases.md)
+ Creación de informes y análisis {#analytics}
   + [Seguimiento y monitorización](start/tracking.md)
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
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Activadores de Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
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
+ Arquitectura y configuración {#config}
   + Arquitectura {#architecture}
      + [Principios globales](architecture/general-architecture.md)
      + [Arquitectura](architecture/architecture.md)
      + Implementación de Snowflake en FDA {#fda}
         + [¿Qué es Snowflake en FDA?](architecture/fda-deployment.md)
      + Implementación empresarial (FDAC) {#ffda}
         + [¿Qué es el FDAC de Campaign?](architecture/enterprise-deployment.md)
         + Características {#ffda-characteristics}
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
      + [Configuración de correo electrónico](config/email-settings.md)
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
      + [Restringir la vista IP](dev/restrict-pi-view.md)
      + [Usar una tabla de destinatarios personalizada](dev/custom-recipient.md)
      + [Actualizar la base de datos](dev/update-database-structure.md)
      + [Formularios de entrada](dev/forms.md)
   + [API de Campaign](dev/api.md)
+ [Panel de control de Campaign >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es)
+ [Guía de automatización de Campaign >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=es)
