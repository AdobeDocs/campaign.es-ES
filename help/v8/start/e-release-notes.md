---
title: Notas de la versión preliminar de Campaign v8
description: Versión preliminar de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: dfc86ebaa2acc0b7777843b2d1d370939b6bfcc2
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---

# Notas de la versión preliminar {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign v8. **Las notas de la versión preliminar que se indican a continuación están sujetas a cambios sin previo aviso hasta la fecha de disponibilidad final de la versión**. Los vínculos, las pantallas y la documentación actualizada se publican en las [notas de la versión](release-notes.md), en la fecha de lanzamiento.

## Versión 8.7.2 {#release-8-7-2}

_miércoles, 30 de julio de 2024_


>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en la [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuevas características {#new-8-7-2}

* **Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y extendido.

* **Notificación push enriquecida (GA)**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push.md).

* **Promoción de marca**: las opciones de promoción de marca ya están disponibles para todos los canales, incluidos los SMS y el correo directo. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=es){target="_blank"}


### Correcciones {#fixes-8-7-2}

En esta versión se han solucionado los siguientes problemas:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-78134, NEO-72915, NEO-77000, NEO-76926, NEO-77002, NEO-76955, NEO-76864, NEO-76495, NEO-O, NEO-77168, NEO-41058, NEO-73602, NEO-75581, NEO-74647, NEO-74585 NEO-, NEO O-74586 74831 77319 78607, NEO O-.

## Versión 8.6.3 {#release-8-6-3}

_miércoles, 30 de julio de 2024_


### Nuevas características {#new-8-6-3}

* **Notificación push enriquecida**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push.md).

* A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. [Más información](release-notes.md#change-8-7-1)


### Mejoras generales {#improvements-8-6-3}

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS ahora se admite para llamadas de API externas.

### Correcciones {#fixes-8-6-3}

En esta versión se han solucionado los siguientes problemas:

NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->