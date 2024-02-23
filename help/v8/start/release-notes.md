---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3b790305984436f1168f9c73aa09df509b2217f0
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 16%

---

# Último lanzamiento{#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. El Adobe recomienda encarecidamente a todos los clientes que actualicen a la versión más reciente. Obtenga más información sobre las versiones y recomendaciones de Campaign [en esta página](upgrades.md).

Como usuario de Cloud Service administrados, la instancia se actualiza por Adobe con cada nueva versión. El Adobe se pondrá en contacto con usted y actualizará sus entornos. Consola del cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

Además, como cliente de, asegúrese de que está utilizando las últimas versiones compatibles de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).


## Versión 8.6.2 {#release-8-6-2}

_23 de febrero de 2024_

### Correcciones {#fixes-8-6-2}

Esta versión corrige el siguiente problema:

* Se ha corregido un problema de rendimiento que podría producirse en la instancia de intermediario (NEO-72595).

## Versión 8.6.1 {#release-8-6-1}

_14 de febrero de 2024_

### Nuevas funciones {#new-8-6-1}

* A partir de esta versión, tendrá acceso a la nueva **Interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe. Desde su intuitiva interfaz, puede acceder rápidamente a sus aplicaciones, funciones de productos y servicios en la nube. Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz web de Adobe Campaign [en esta página](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 ahora se integra con **Adobe Experience Manager as a Cloud Service**, con la creación exclusivamente disponible a través de la interfaz de usuario web de Adobe Campaign. [Más información](../connect/ac-aem.md)

* Ahora puede utilizar su **Biblioteca de Adobe Experience Manager Assets** junto con los recursos de su Experience Cloud, incluso si el paquete Integration with the Adobe Experience Cloud está instalado en la instancia de Adobe Campaign. [Más información](../connect/ac-aem.md#assets-library)

### Mejoras generales {#improvements-8-6-1}

* Campaign v8.6 ofrece un rendimiento mejorado para **indicadores de seguimiento de envíos de correo electrónico**. Con nuestros procesos optimizados, el seguimiento de la ingesta y el tiempo de cálculo se reducen, y puede comprobar los indicadores clave de entrega mucho más rápido.


### Actualizaciones de entrega {#deliverability-8-6-1}

* En febrero de 2024, cualquier empresa que envíe más de 5000 mensajes de correo electrónico a través de Google o Yahoo! tendrá que empezar a utilizar una tecnología de autenticación conocida como Sistema de informes y conformidad de autenticación de mensajes basado en dominio (DMARC). Asegúrese de tener configurado el registro DMARC para todos los subdominios que utilice con Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=es){target="_blank"}

* A partir del 1 de junio de 2024, Google y Yahoo! exigirá a los remitentes que cumplan con la cancelación de la suscripción a una lista de un clic. Adobe Campaign ahora admite esta opción. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Correcciones {#fixes-8-6-1}

Los siguientes problemas se encuentran en esta versión: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-63815, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059 58637 55197 52542 50488 47789 O-, NEO O-, NEO O-, NEO O-, NEO O-, NEO O-, NEO O-