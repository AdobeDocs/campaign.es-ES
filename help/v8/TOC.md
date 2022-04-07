---
audience: end-user
user-guide-title: Campaign v8
description: Documentación de Campaign v8
breadcrumb-title: Campaign v8
title: Documentos de Campaign v8
source-git-commit: c3beb735f54606537bcc977f2f0539767d15b2d9
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 81%

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
   + Interfaz de usuario de Campaign {#ac-ui}
      + [Descubra la interfaz de Campaign](start/campaign-ui.md)
      + [Personalización de la interfaz de Campaign](start/customize-ui.md)
   + [Trabajar con audiencias](start/audiences.md)
   + [Importación de datos](start/import.md)
   + [Creación de campañas](start/campaigns.md)
   + [Envío de mensajes](start/create-message.md)
   + [Administración de las suscripciones](start/subscriptions.md)
   + [Seguimiento y monitorización](start/tracking.md)
   + [Métricas e informes](start/reporting.md)
   + [Preguntas frecuentes](start/campaign-faq.md)
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
   + [Perfiles de acceso](audiences/view-profiles.md)
   + Adición de perfiles {#add-profiles}
      + [Crear perfiles manualmente](audiences/create-profiles.md)
      + [Importar perfiles de un archivo](audiences/import-profiles.md)
      + [Trabajar con perfiles externos](audiences/external-profiles.md)
      + [Recopilación de datos de perfil en formularios web](audiences/collect-profiles.md)
   + Creación de audiencias {#create-audiences}
      + [Crear una lista de contactos](audiences/create-audiences.md)
      + [Crear y administrar filtros](audiences/create-filters.md)
   + [Administrar carpetas y vistas](audiences/folders-and-views.md)
   + [Prácticas recomendadas](audiences/audiences-best-practices.md)
+ Envío de mensajes{#send}
   + [Correos electrónicos](send/email.md)
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
   + [Administración de datos](config/replication.md)
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
   + [Campaign + su CRM](connect/crm.md)
+ Recursos para desarrolladores {#architecture}
   + [Principios globales](dev/general-architecture.md)
   + [Arquitectura](dev/architecture.md)
   + [Modelo de datos](dev/datamodel.md)
   + Esquemas y formularios {#shemas-forms}
      + [Usar esquemas](dev/schemas.md)
      + [Administración de claves y unicidad](dev/keys.md)
      + [Crear esquemas](dev/create-schema.md)
      + [Ampliar esquemas](dev/extend-schema.md)
      + [Filtrar esquemas](dev/filter-schema.md)
      + [Estructura del esquema](dev/schema-structure.md)
      + [Asignación de base de datos](dev/database-mapping.md)
      + [Restringir la vista IP](dev/restrict-pi-view.md)
      + [Usar una tabla de destinatarios personalizada](dev/custom-recipient.md)
      + [Actualizar la base de datos](dev/update-database-structure.md)
      + [Formularios de entrada](dev/forms.md)
   + API {#api}
      + [Introducción](dev/api.md)
      + [Nuevas API](dev/new-apis.md)
      + [Mecanismo de ensayo de API](dev/staging.md)
+ [Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es)
