---
product: Adobe Campaign
title: Envío de notificaciones push con Adobe Campaign
description: Introducción a las notificaciones push en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 17%

---

# Creación y envío de notificaciones push

Los envíos de aplicaciones móviles permiten enviar notificaciones a sistemas iOS y Android.

Para enviar notificaciones push en Adobe Campaign, debe:

1. Configuración del entorno de Campaign
1. Cree un servicio de información de tipo aplicación móvil para su aplicación móvil.
1. Añada a este servicio las versiones de iOS y Android de la aplicación.
1. Cree un envío tanto para iOS como para Android.

[!DNL :arrow_upper_right:] Obtenga información sobre cómo empezar a utilizar la aplicación móvil en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integración con el SDK de Adobe

### Integración del SDK de Campaign

El SDK de Campaign facilita la integración de la aplicación móvil en la plataforma Adobe Campaign.

[!DNL :arrow_upper_right:] Obtenga información sobre cómo integrar el SDK de Campaign con su aplicación en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configurar la extensión de Campaign en Launch

Puede integrar el SDK de Launch de Adobe Experience Platform con Campaign, aprovechando la extensión de Campaign Classic.

[!DNL :arrow_upper_right:] Obtenga más información en la documentación del SDK de Mobile de  [Adobe](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configuración de la aplicación en Campaign

Debe definir la configuración de las aplicaciones de iOS y Android en Adobe Campaign.

[!DNL :arrow_upper_right:] Las directrices de configuración para iOS se detallan en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

[!DNL :arrow_upper_right:] Las directrices de configuración para Android se detallan en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Creación de la primera notificación push

[!DNL :arrow_upper_right:] Aprenda a crear sus primeras notificaciones push en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Con el registro móvil de Campaign v8 ahora es **asíncrono**. [Más información](../dev/staging.md)
