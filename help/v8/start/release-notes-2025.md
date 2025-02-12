---
title: Notas de la versión de Campaign v8 (consola) 2025
description: Lista de funciones y mejoras incluidas en las versiones de Campaign v8 de 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 82622a4517356eaba1f7eba23d4b3050d8ca37c9
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 90%

---

# Notas de la versión 2025 {#2025-rn}

Esta página lista las nuevas funcionalidades, mejoras y correcciones incluidas en las **versiones de Campaign v8 de 2025**. Las versiones más recientes se enumeran en [esta página](release-notes.md).

## Versión 8.7.2 {#release-8-7-2}

_3 de septiembre de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en la [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#new-8-7-2}

* **Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y ampliado. [Más información](../send/sms/sms.md).

* **Notificación push enriquecida (GA)**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push-android.md).

* **Promoción de la marca**: las opciones de promoción de la marca ya están disponibles para todos los canales, incluidos SMS y correo directo. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=es){target="_blank"}

### Correcciones {#fixes-8-7-2}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843 y NEO-79328.
