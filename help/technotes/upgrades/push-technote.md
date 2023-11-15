---
product: campaign
title: Próximos cambios del canal de notificaciones push
description: Próximos cambios del canal de notificaciones push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="También se aplica a Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Se aplica a Campaign v8"
hide: true
hidefromtoc: true
source-git-commit: 65b8d84e600e1814484fa81fb814475c0a8b9296
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 19%

---

# Próximos cambios del canal de notificaciones push {#push-upgrade}

Puede utilizar Campaign para enviar notificaciones push a dispositivos Android. Para ello, Campaign se basa en servicios de suscripción específicos. Algunos cambios importantes en el servicio Android Firebase Cloud Messaging (FCM) se lanzarán en 2024 y pueden afectar a su implementación de Adobe Campaign. Es posible que sea necesario actualizar la configuración de los servicios de suscripción para los mensajes push de Android a fin de admitir este cambio.

## ¿Qué ha cambiado? {#fcm-changes}

Como parte del esfuerzo continuo de Google por mejorar sus servicios, las API de FCM heredadas dejarán de usarse el **20 de junio de 2024**. Obtenga más información acerca del protocolo HTTP de Firebase Cloud Messaging en [Documentación de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 y Adobe Campaign v8 ya admiten las últimas API para enviar mensajes de notificación push. Sin embargo, algunas implementaciones antiguas aún dependen de las API heredadas. Estas implementaciones deben actualizarse.

## ¿Se ha visto afectado? {#fcm-impact}

Si la implementación actual admite servicios de suscripción que se conecten a FCM mediante las API heredadas, se verá afectado. La migración a las API más recientes es obligatoria para evitar cualquier interrupción del servicio. En ese caso, los equipos de Adobe se pondrán en contacto con usted.

Para comprobar si se ha visto afectado, puede filtrar su **Servicios y suscripciones** según el filtro siguiente:

![](assets/filter-services-fcm.png)


* Si alguno de los servicios de notificaciones push activos utiliza **HTTP (heredado)** API, su configuración se verá directamente afectada por este cambio. Debe revisar las configuraciones actuales y migrar a las API más nuevas como se describe a continuación.

* Si su configuración utiliza exclusivamente **HTTP v1** API para notificaciones push de Android, entonces ya cumple los requisitos y no se requiere ninguna acción por su parte.

## ¿Cómo realizar la migración? {#fcm-migration-procedure}

### Requisitos previos {#fcm-migration-prerequisites}

* Para Campaign Classic v7, se ha añadido la compatibilidad con HTTP v1 en la versión 20.3.1. Si su entorno se está ejecutando en una versión anterior, un requisito previo para la migración a HTTP v1 es actualizar el entorno a [última compilación de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Para Campaign v8, HTTP v1 es compatible con todas las versiones y no se necesita ninguna actualización.

* El archivo JSON de la cuenta del servicio Android Firebase Admin SDK es necesario para mover la aplicación móvil a HTTP v1. Obtenga información sobre cómo obtener este archivo en [Documentación de Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Para implementaciones híbridas, alojadas y de Managed Services, además del procedimiento de migración que se muestra a continuación, póngase en contacto con el Adobe de para actualizar el servidor de ejecución en tiempo real (RT). El servidor intermediario no se ve afectado.

* Como usuario On-Premise de Campaign Classic v7, debe actualizar los servidores de ejecución de marketing y en tiempo real. El servidor intermediario no se ve afectado.

### Procedimiento de migración {#fcm-migration-steps}

Para migrar su entorno a HTTP v1, siga estos pasos:

1. Vaya a la lista de **Servicios y suscripciones**.
1. Enumerar todas las aplicaciones móviles mediante **HTTP (heredado)** Versión de API.
1. Para cada una de estas aplicaciones móviles, configure el **Versión de API** hasta **HTTP v1**.
1. Haga clic en **[!UICONTROL Load project json file to extract project details...]** para cargar directamente el archivo con clave JSON.

   También puede introducir manualmente los siguientes detalles:

   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Haga clic en **[!UICONTROL Test the connection]** para comprobar que la configuración es correcta y que el servidor de marketing tiene acceso a FCM. Tenga en cuenta que para las implementaciones intermediarias, la variable **[!UICONTROL Test connection]** El botón no puede comprobar si el servidor tiene acceso al servicio Firebase Cloud Messaging (FCM) de Android.
1. Como opción, puede enriquecer el contenido de un mensaje push con algunos **[!UICONTROL Application variables]** si es necesario. Son totalmente personalizables y una parte de la carga útil de mensajes se envía al dispositivo móvil.
1. Haga clic en **[!UICONTROL Finish]** y luego en **[!UICONTROL Save]**.

A continuación se muestran los nombres de carga útil de FCM para personalizar aún más la notificación push. Estas opciones están detalladas [aquí](#fcm-apps).

| Tipo de mensaje | Elemento de mensaje configurable (nombre de carga útil de FCM) | Opciones configurables (nombre de carga útil de FCM) |
|:-:|:-:|:-:|
| mensaje de datos | N/A | validate_only |
| mensaje de notificación | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Una vez aplicados estos cambios en todos los servidores, todos los nuevos envíos de notificaciones push a dispositivos Android utilizan la API HTTP v1. Los envíos push existentes en reintento, en curso y en uso siguen utilizando la API HTTP (heredada).

### ¿Cuál es el impacto para mis aplicaciones de Android? {#fcm-apps}

No se requieren cambios específicos en el código de las aplicaciones móviles Android y el comportamiento de las notificaciones no debe cambiar.

Sin embargo, con HTTP v1, puede personalizar aún más la notificación push con **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

Puede hacer lo siguiente:

* Utilice el **[!UICONTROL Ticker]** para establecer el texto del valor de la notificación.
* Utilice el **[!UICONTROL Image]** para establecer la dirección URL de la imagen que se mostrará en la notificación.
* Utilice el **[!UICONTROL Notification Count]** para establecer la cantidad de información nueva no leída que se mostrará directamente en el icono de la aplicación.
* Configure las variables **[!UICONTROL Sticky]** Opción a false para que la notificación se descarte automáticamente cuando el usuario haga clic en ella. Si se establece en true, la notificación se seguirá mostrando incluso cuando el usuario haga clic en ella.
* Configure las variables **[!UICONTROL Notification Priority]** nivel de la notificación al predeterminado, mínimo, bajo o alto.
* Configure las variables **[!UICONTROL Visibility]** nivel de notificación a público, privado o secreto.

Para obtener más información sobre **[!UICONTROL HTTP v1 additional options]** y cómo rellenar estos campos, consulte la [documentación de FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

