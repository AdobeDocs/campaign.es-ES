---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 07e0bfdade0356eedb24641259aa754fdb1c6155
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 78%

---

# Últimas versiones {#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Adobe recomienda encarecidamente a todos sus clientes que actualicen a la versión más reciente. Esta página lista las nuevas funciones, mejoras y correcciones que se proporcionan con las últimas versiones de Campaign v8 (Console). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md).

Como usuario de Cloud Services administrados, su instancia se actualiza en Adobe con cada nueva versión. Adobe se pondrá en contacto con usted y actualizará sus entornos. La consola cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola del cliente en [esta página](../start/connect.md#upgrade-ac-console).

Además, como cliente, asegúrese de que utiliza la última versión compatible de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).


## Versión 8.7.2 {#release-8-7-2}

_3 de septiembre de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en la [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuevas características {#new-8-7-2}

* **Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y extendido. [Más información](../send/sms/sms.md).

* **Notificación push enriquecida (GA)**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push-android.md).

* **Promoción de marca**: las opciones de promoción de marca ya están disponibles para todos los canales, incluidos los SMS y el correo directo. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=es){target="_blank"}


### Correcciones {#fixes-8-7-2}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.


## Versión 8.6.3 {#release-8-6-3}

_30 de julio de 2024_

### Nuevas características {#new-8-6-3}

* **Notificaciones push enriquecidas**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push-android.md).

* A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. [Más información](release-notes-2024.md#change-8-7-1)

### Mejoras generales {#improvements-8-6-3}

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS se admite ahora para llamadas de API externas.

### Correcciones {#fixes-8-6-3}

En esta versión se han solucionado los siguientes problemas:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596 y NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->
