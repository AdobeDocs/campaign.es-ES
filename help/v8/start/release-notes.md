---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 607ef2ab8f1f1c7400451019e188c70f8c7d6091
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 74%

---

# Último lanzamiento{#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Adobe recomienda encarecidamente a todos sus clientes que actualicen a la versión más reciente. 

Como usuario de Cloud Services administrados, su instancia se actualiza en Adobe con cada nueva versión. Adobe se pondrá en contacto con usted y actualizará sus entornos. La consola cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtén información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

Además, como cliente, asegúrese de que utiliza la última versión compatible de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).

## Versión 8.5.3 {#release-8-5-3}

_miércoles, 28 de mayo de 2024_

### Migración a las credenciales de servidor a servidor OAuth {#change-8-5-3}

* A partir de esta versión, con la credencial de cuenta de servicio (JWT) obsoleta por el Adobe, las integraciones salientes de Campaign con soluciones de Adobe y aplicaciones ahora dependen de la credencial de servidor a servidor OAuth. Adobe realizará la migración de JWT a OAuth para sus integraciones salientes, como la integración de Campaign-Analytics o la integración de Experience Cloud Déclencheur.

  Si ha implementado integraciones entrantes con Campaign, debe migrar su cuenta técnica como se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio existente (JWT) seguirán funcionando hasta que **27 de enero de 2025**. Además, Developer Console seguirá admitiendo la creación de nuevas credenciales de cuenta de servicio (JWT) hasta **3 de junio de 2024**. No se puede crear ni agregar una nueva credencial de cuenta de servicio (JWT) a un proyecto después de esta fecha.


### Correcciones {#fixes-8-5-3}

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542

## Versión 8.7.1 {#release-8-7-1}

_2 de mayo de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en la [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nuevas características {#new-8-7-1}

* **Plantillas de notificaciones push enriquecidas**: ahora puede enviar notificaciones push enriquecidas a través de Android. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. [Más información](../send/rich-push.md).

* **Promoción de la marca**: como usuario migrado de Campaign Standard, ahora los administradores técnicos pueden definir una o varias marcas para centralizar los parámetros que afectan a la identidad de una marca. Esto incluye el logotipo de la marca, el dominio de la URL de acceso de la página de aterrizaje o la configuración del seguimiento de mensajes. Con Adobe Campaign, puede crear estas marcas y vincularlas a mensajes o páginas de aterrizaje. Esta configuración se administra en plantillas. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=es){target="_blank"}

* **API de REST**: como usuario migrado de Campaign Standard, puede utilizar las API de REST para crear integraciones para Adobe Campaign y generar su propio ecosistema interconectando Adobe Campaign con el panel de tecnologías que emplea. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=es){target="_blank"}

* **Creación de informes dinámicos**: como usuario migrado de Campaign Standard, puede acceder a la Creación de informes dinámicos, que proporciona informes totalmente personalizables y en tiempo real para medir el impacto de sus actividades de marketing. Añade acceso a los datos del perfil, lo que permite el análisis demográfico por dimensiones de perfil como sexo, ciudad y edad, además de datos funcionales de campaña de correo electrónico como aperturas y clics. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=es){target="_blank"}

* **Nuevo complemento de seguridad mejorada**: Para hacer que la conexión de red sea más segura y proporcionar una seguridad mejorada para sus recursos, Adobe Campaign ofrece un nuevo complemento de seguridad mejorada, que incluye dos funciones: integración CMK segura y túnel VPN seguro. [Más información](../config/enhanced-security.md)


### Actualizaciones de compatibilidad {#comp-8-7-1}

* Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA). Obtenga más información [en esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* A partir de esta versión, con la credencial de cuenta de servicio (JWT) obsoleta por el Adobe, las integraciones salientes de Campaign con soluciones de Adobe y aplicaciones ahora dependen de la credencial de servidor a servidor OAuth. Adobe realizará la migración de JWT a OAuth para sus integraciones salientes, como la integración de Campaign-Analytics o la integración de Experience Cloud Déclencheur.

  Si ha implementado integraciones entrantes con Campaign, debe migrar su cuenta técnica como se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio existente (JWT) seguirán funcionando hasta que **27 de enero de 2025**. Además, Developer Console seguirá admitiendo la creación de nuevas credenciales de cuenta de servicio (JWT) hasta **3 de junio de 2024**. No se puede crear ni agregar una nueva credencial de cuenta de servicio (JWT) a un proyecto después de esta fecha.


### Mejoras generales {#improvements-8-7-1}

* Se han cambiado varios esquemas de 32 a 64 bits. Esto solo se aplica a los clientes que migran de Campaign Standard. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=es){target="_blank"}

* En las tablas de Campaign, los siguientes atributos ahora se rellenan de forma predeterminada por la fecha y la hora del servidor: `lastModified` y `created`. El `createdBy-id` El valor del atributo ahora se rellena con el ID de inicio de sesión actual de forma predeterminada. Los valores proporcionados por los usuarios en las llamadas de API se ignoran. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Correcciones {#fixes-8-7-1}

Se ha corregido los siguientes problemas en esta versión: 
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

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