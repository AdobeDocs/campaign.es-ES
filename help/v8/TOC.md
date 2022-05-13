---
audience: end-user
user-guide-title: Campaign v8
description: Documentación de Campaign v8
breadcrumb-title: Campaign v8
title: Documentos de Campaign v8
source-git-commit: d7e0635c6fccd70ed012a5b8148258383a1f6766
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 90%

---


# Documentación de Adobe Campaign v8 {#campaign-v8}

+ [Documentación de Campaign v8](campaign-home.md)
+ Novedades {#new}
   + [Funcionalidades clave](start/whats-new.md)
   + [Notas de la versión](start/release-notes.md)
   + [Limitaciones conocidas](start/known-limitations.md)
   + [Classic v7 a v8](start/capability-matrix.md)
+ Inicio {#start}
   + [Introducción](start/get-started.md)
   + [Componentes y procesos](start/ac-components.md)
   + IU de Campaign {#ac-ui}
      + [Descubrimiento de la interfaz de Campaign](start/campaign-ui.md)
      + [Personalización de la interfaz de Campaign](start/customize-ui.md)
   + [Trabajo con audiencias](start/audiences.md)
   + [Administración de solicitudes de privacidad](start/privacy.md)
   + [Importación de datos](start/import.md)
   + [Creación de campañas](start/campaigns.md)
   + [Envío de mensajes](start/create-message.md)
   + [Administración de las suscripciones](start/subscriptions.md)
   + [Seguimiento y monitorización](start/tracking.md)
   + [Métricas e informes](start/reporting.md)
   + [Preguntas frecuentes](start/campaign-faq.md)
+ Arquitectura {#architecture}
   + [Principios globales](architecture/general-architecture.md)
   + [Arquitectura](architecture/architecture.md)
   + {#fda}
      + [What is FDA-Snowflake?](architecture/fda-deployment.md)
   + {#ffda}
      + [What is Campaign FFDA?](architecture/enterprise-deployment.md)
      + {#ffda-characteristics}
         + [Administración de claves y unicidad](architecture/keys.md)
         + [Nuevas API](architecture/new-apis.md)
         + [Mecanismo de ensayo de API](architecture/staging.md)
         + [Replication mechanism](architecture/replication.md)
+ Implementar {#implement}
   + [Pasos de implementación](start/implement.md)
   + [Personalizar la instancia](dev/customize.md)
   + [Directrices de seguridad](config/security.md)
   + [Diseño de aplicaciones y formularios web](dev/webapps.md)
   + [Prácticas recomendadas del modelo de datos](dev/datamodel-best-practices.md)
+ Implementar {#deploy}
   + [Matriz de compatibilidad](start/compatibility-matrix.md)
   + [Conexión a Campaign](start/connect.md)
   + [Permisos](start/permissions.md)
   + [Panel de control de Campaign](config/self-service.md)
+ Perfiles y audiencias {#profiles-and-audiences}
   + [Introducción](audiences/gs-audiences.md)
   + [Acceso a perfiles](audiences/view-profiles.md)
   + Adición de perfiles {#add-profiles}
      + [Creación de perfiles manual](audiences/create-profiles.md)
      + [Importación de perfiles de un archivo](audiences/import-profiles.md)
      + [Trabajo con perfiles externos](audiences/external-profiles.md)
      + [Recopilación de datos de perfil en formularios web](audiences/collect-profiles.md)
   + Creación de audiencias {#create-audiences}
      + [Creación de una lista de contactos](audiences/create-audiences.md)
      + [Creación y administración de filtros](audiences/create-filters.md)
   + [Administración de carpetas y vistas](audiences/folders-and-views.md)
   + [Prácticas recomendadas](audiences/audiences-best-practices.md)
+ Envío de mensajes{#send}
   + Correos electrónicos {#emails}
      + [Design and send emails](send/email.md)
      + [Envío con el servidor de correo mejorado](send/enhanced-mta.md)
   + [SMS](send/sms.md)
   + [Notificaciones push](send/push.md)
   + [Mensajería LINE](send/line.md)
   + [Correo directo](send/direct-mail.md)
   + [Marketing social](send/twitter.md)
   + [Mensajes transaccionales](send/transactional.md)
   + Errores, rechazos y cuarentenas{#failures}
      + [Cuarentenas](send/quarantines.md)
      + [Errores de entrega](send/delivery-failures.md)
+ Interacción en tiempo real{#interaction}
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
   + [Enviar una oferta (saliente)](interaction/interaction-send-offers.md)
   + Presentación de una oferta (entrante){#inbound}
      + [Contexto](interaction/interaction-present-offers.md)
      + [Invocación de una oferta en una página web](interaction/interaction-integration.md)
      + [Administración de interacciones anónimas](interaction/anonymous-interactions.md)
   + [Informes e historial](interaction/interaction-tracking.md)
   + [Casos de uso](interaction/interaction-use-cases.md)
+ Configurar {#config}
   + [Automatización con flujos de trabajo](config/workflows.md)
   + [Configuración de correo electrónico](config/email-settings.md)
   + [Configuración de mensajería transaccional](config/transactional-msg-settings.md)
   + [Integración de los SDK de Campaign con la aplicación](config/push-config.md)
   + [Cuentas externas](config/external-accounts.md)
+ Conectar {#connect}
   + [Conectar con otras soluciones](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Activadores de Experience Cloud](connect/ac-triggers.md)
   + [Campaign + RTCDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + Base de datos externa](connect/fda.md)
   + Campaign + su CRM {#ac-crm}
      + [Introducción a los conectores CRM](connect/crm.md)
      + [Work with Campaign and SFDC](connect/ac-sfdc.md)
      + [Work with Campaign and Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Synchronize data](connect/crm-data-sync.md)
+ Recursos para desarrolladores {#developer}
   + [Campaign datamodel](dev/datamodel.md)
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
+ [Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es)

