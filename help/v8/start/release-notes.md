---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 520a7798cd1969e7c29519cbc918b66a44ff2a71
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 51%

---

# Último lanzamiento{#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. El Adobe recomienda encarecidamente a todos los clientes que actualicen a la versión más reciente.

Como usuario de Cloud Services administrados, su instancia se actualiza en Adobe con cada nueva versión. Adobe se pondrá en contacto con usted y actualizará sus entornos. La consola cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

Además, como cliente de, asegúrese de que está utilizando las últimas versiones compatibles de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).

## Versión 8.7.1 {#release-8-7-1}

_viernes, 02 de mayo de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a Adobe Campaign v8** y no se pueden implementar en ningún otro entorno.
>
>Consulte las siguientes páginas de documentación: [Campaign Standard de la transición a Campaign v8](https://experienceleague.adobe.com/en/docs/campaign-web/v8/release-notes/acs-migration) y [Funciones para usuarios de Campaign Standard](https://experienceleague.adobe.com/docs/experience-cloud/campaign/campaign-standard-migration-home.html).

### Nuevas características {#new-8-7-1}

* **Plantillas de notificaciones push enriquecidas** : Ahora puede enviar notificaciones push enriquecidas a través de Android. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los mensajes de texto simples mediante la incorporación de elementos multimedia como imágenes, botones interactivos u otro contenido multimedia enriquecido. [Más información](../send/rich-push.md)

* **Marca** - Como usuario Campaign Standard migrado, los administradores técnicos ahora pueden definir una o varias marcas para centralizar los parámetros que afectan a la identidad de una marca. Esto incluye el logotipo de la marca, el dominio de la URL de acceso de la página de aterrizaje o la configuración del seguimiento de mensajes. Puede crear estas marcas y vincularlas a mensajes o páginas de aterrizaje. Esta configuración se administra en plantillas. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html)

* **API de REST** : Como usuario Campaign Standard migrado, puede utilizar las API de REST para crear integraciones para Adobe Campaign y construir su propio ecosistema al interconectar Adobe Campaign con el panel de tecnologías que utiliza. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html)

* **Informes dinámicos** : Como usuario Campaign Standard migrado, puede acceder a la Creación de informes dinámicos, que proporciona informes totalmente personalizables y en tiempo real para medir el impacto de sus actividades de marketing. Añade acceso a los datos de perfil, lo que permite el análisis demográfico por dimensiones de perfil como sexo, ciudad y edad, además de datos funcionales de campaña de correo electrónico como aperturas y clics. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html)

<!--
* **New Enhanced security add-on**: To make your network connection more secure and provide improved security for your resources, Adobe Campaign offers a new Enhanced security add-on, which includes two features: Secure CMK integration and Secure VPN tunneling.
-->

### Actualizaciones de compatibilidad {#comp-8-7-1}

Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA). Obtenga más información sobre FDA en [esta página](../connect/fda.md).

### Mejoras generales {#improvements-8-7-1}

* Se han cambiado varios esquemas de 32 a 64 bits. Esto solo se aplica a los clientes que migran de Campaign Standard. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html).

* En las tablas de Campaign, un nuevo indicador le permite gestionar las modificaciones de los atributos lastModified, created y createdBy-id. Cuando el indicador está activado, se omiten los valores proporcionados por los usuarios a estos atributos. Solo se utilizan la hora del servidor y el ID del contexto de usuario. Cuando el indicador está desactivado, se utilizan los valores proporcionados por el usuario para estos atributos. El indicador ignoreTimestampsID se encuentra en serverConf.xml, en el nodo &quot;compartido&quot;.

### Correcciones {#fixes-8-7-1}

Los siguientes problemas se encuentran en esta versión: NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-67620, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054,-------,--,, o,,------------,-----,--,,,-------------,, y, y, y,--, y, y, y, y, y, y, y, y, y, y, de-o--o-o-o-o--o-o-o-o

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