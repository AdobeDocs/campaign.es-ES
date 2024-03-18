---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3a63539bc6bb20fa79bdac76dd60efe7b232458b
workflow-type: ht
source-wordcount: '478'
ht-degree: 100%

---

# Último lanzamiento{#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Adobe recomienda encarecidamente a todos sus clientes que actualicen a la versión más reciente. Obtenga más información sobre versiones y recomendaciones de Campaign [en esta página](upgrades.md).

Como usuario de Cloud Services administrados, su instancia se actualiza en Adobe con cada nueva versión. Adobe se pondrá en contacto con usted y actualizará sus entornos. La consola cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola cliente [en esta página](../start/connect.md#upgrade-ac-console).

Además, como cliente, asegúrese de que está utilizando la última versión compatible de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).


## Versión 8.6.2 {#release-8-6-2}

_23 de febrero de 2024_

### Correcciones {#fixes-8-6-2}

Esta versión corrige el siguiente problema:

* Se ha corregido un problema de rendimiento que podría producirse en la instancia de intermediario (NEO-72595).

## Versión 8.6.1 {#release-8-6-1}

_14 de febrero de 2024_

### Nuevas características {#new-8-6-1}

* A partir de esta versión, tendrá acceso a la nueva **Interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe. Desde su intuitiva interfaz, puede acceder rápidamente a sus aplicaciones, funciones de productos y servicios en la nube. Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz de Adobe Campaign Web [en esta página](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 ahora se integra con **Adobe Experience Manager as a Cloud Service**, con la creación exclusivamente disponible a través de la interfaz de usuario web de Adobe Campaign. [Más información](../connect/ac-aem.md)

* Ahora puede utilizar su **Biblioteca de recursos de Adobe Experience Manager** junto con los recursos de su Experience Cloud, incluso si el paquete Integración con Adobe Experience Cloud está instalado en la instancia de Adobe Campaign. [Más información](../connect/ac-aem.md#assets-library)

### Mejoras generales {#improvements-8-6-1}

* Campaign v8.6 ofrece un rendimiento mejorado para **indicadores de seguimiento de envíos de correo electrónico**. Con nuestros procesos optimizados, el seguimiento de la ingesta y el tiempo de cálculo se reducen, y puede comprobar los indicadores clave de envío mucho más rápido.


### Actualizaciones de la entregabilidad {#deliverability-8-6-1}

* En febrero de 2024, cualquier compañía que envíe más de 5000 mensajes de correo electrónico a través de Google o Yahoo! tendrá que empezar a utilizar una tecnología de autenticación conocida como Domain based Message Authentication, Reporting and Conformance (DMARC). Asegúrese de tener configurado el registro DMARC para todos los subdominios que utilice con Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=es){target="_blank"}

* A partir del 1 de junio de 2024, Google y Yahoo! exigirán a los remitentes que cumplan con la cancelación de la suscripción a una lista en un clic. Adobe Campaign ahora admite esta opción. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=es#one-click-list-unsubscribe){target="_blank"}


### Correcciones {#fixes-8-6-1}

Los siguientes problemas se encuentran en esta versión: 
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-63815, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO- 58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789