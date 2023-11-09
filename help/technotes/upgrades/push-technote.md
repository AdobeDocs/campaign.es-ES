---
product: campaign
title: Próximos cambios del canal de notificaciones push
description: Próximos cambios del canal de notificaciones push
hide: true
hidefromtoc: true
source-git-commit: 11330ed8e79ec256b158747914f178b8b6857a33
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Próximos cambios del canal de notificaciones push {#push-upgrade}

En esta página se describen los próximos cambios en el canal de notificaciones push mediante Firebase Cloud Messaging en Adobe Campaign Classic.

Existen cambios importantes en el servicio Firebase Cloud Messaging (FCM) que pueden afectar a su implementación de Adobe Campaign Classic.

Como parte del esfuerzo continuo de Google por mejorar sus servicios, las API heredadas de FCM se suspenderán en junio de 2024 (Protocolo HTTP de Firebase Cloud Messaging: https://firebase.google.com/docs/cloud-messaging/http-server-ref)

Actualmente, estas API están integradas con Adobe Campaign Classic para enviar mensajes de notificación push. Entendemos que muchos de nuestros clientes, como usted, confían en estos servicios para sus campañas de marketing y necesidades de comunicación y especialmente para dispositivos Android.

## ¿Cómo Le Afecta Esto?

* **Usuarios de API de HTTP (heredada)**: Si alguna de sus campañas de notificación push activas utiliza la API HTTP (heredada), su configuración se verá directamente afectada por este cambio. Le recomendamos encarecidamente que revise sus configuraciones actuales y se prepare para la migración a las API más nuevas.

* **Buenas noticias para los usuarios de la API HTTP v1**: Si la configuración utiliza exclusivamente la API HTTP v1 para las notificaciones push de Android, ya cumple los requisitos y no es necesario que realice más acciones.

## ¿Qué Estamos Haciendo?

* **Plan de transición**: Nuestro equipo está trabajando activamente en el desarrollo de un plan de transición integral. Esto garantizará que, cuando sea necesario, pueda actualizar la implementación a las API de FCM más nuevas ya disponibles en versiones recientes de Adobe Campaign y con una interrupción mínima de sus campañas.

* **Instrucciones detalladas**: Proporcionaremos una guía paso a paso y otros recursos para facilitar un proceso de transición sin problemas.

* **Asistencia**: nuestro equipo de asistencia al cliente estará disponible para ayudarle durante esta transición. También podemos organizar seminarios web y sesiones de capacitación para cubrir los aspectos técnicos y las mejores prácticas para la transición.

## ¿Cómo Le Afecta Esto?

* **Manténgase informado**: observe su bandeja de entrada para recibir más comunicaciones nuestras, incluido el plan de transición detallado.

* **Revisar configuración actual**: Tómese este tiempo para revisar la configuración y personalización actuales en Adobe Campaign Classic, de modo que esté preparado para realizar los cambios necesarios si es necesario.

* **Contáctenos.**: Si tiene alguna duda o pregunta inmediata, no dude en ponerse en contacto con nuestro equipo de asistencia.

## Pasos de implementación

En las próximas semanas, compartiremos más detalles sobre el plan de transición para las API de FCM heredadas, incluidos los plazos y los elementos de acción. Tenga la seguridad de que nuestro objetivo principal es hacer que esta transición sea lo más fluida posible para usted y su equipo.

Apreciamos su negocio y le agradecemos su comprensión a medida que nos adaptamos a estos cambios. Su éxito es nuestra máxima prioridad, y estamos comprometidos a apoyarle en cada paso del camino.

Para poder anticipar el cambio, estos son los pasos generales que se necesitarán para migrar la configuración push de HTTP (heredada) a la API HTTPv1 de FCM.

### Actualización de compilación

* Campaign Classic: la compatibilidad con HTTPv1 se ha añadido en la versión AC7 20.3.1. Si utiliza una versión anterior, primero debe actualizar a la última versión de Campaign Classic.

* Campaign v8: HTTPv1 es compatible con todas las versiones de Campaign v8. No se necesita ninguna actualización.

### Servidor de marketing

Los cambios de configuración los puede realizar el cliente o el socio.

1. En primer lugar, debe extraer el archivo JSON. El archivo JSON de la cuenta del servicio Firebase Admin SDK es necesario para mover la aplicación móvil a HTTPv1. Consulte [esta página](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Navegue hasta la lista de **Servicios y suscripciones**.

1. Localice todas las aplicaciones móviles mediante la versión de la API HTTP (heredada).

1. Para cada una de estas aplicaciones móviles, configure el **Versión de API** Vaya a HTTPv1 y siga las instrucciones de configuración detalladas en la [documentación](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>El cambio a la API HTTPv1 se tiene en cuenta para los nuevos envíos. Los envíos en reintento, en curso y en uso seguirán utilizando la API HTTP (heredada).

### Mid Sourcing Server

No se requieren cambios.

### Servidor de ejecución en tiempo real

Debe ponerse en contacto con el servicio de asistencia de Adobe Campaign para obtener esto. El procedimiento de migración es el mismo que para el servidor de marketing.

### Sistema operativo y aplicación móvil de Android

No se requieren cambios específicos en el código de las aplicaciones móviles Android y el comportamiento de las notificaciones no debe cambiar.

Sin embargo, HTTPv1 introduce tres nuevos elementos de carga útil:

| Nombre | Valor predeterminado |
|---|---|
| pegajoso | Falso |
| prioridad | Predeterminado |
| visibilidad | Falso |
| pegajoso | Privada |
