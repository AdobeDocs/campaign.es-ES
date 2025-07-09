---
title: Notas de la versión de la version 8 de Campaign de 2024 (consola)
description: Lista de funciones y mejoras incluidas en las versiones de Campaign v8 de 2024
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 91%

---

# Notas de la versión 2024 {#2024-rn}

En esta página se indican las nuevas funcionalidades, mejoras y correcciones que se incluyen con la **la versión 8 de Campaign de 2024**. Para obtener la última versión, consulte [esta página](release-notes.md).

Para cualquier implementación nueva o actualización a un entorno existente, instale [la versión más reciente](release-notes.md).


>[!BEGINSHADEBOX]

**En esta página**

* Versión 8.7 de Campaign: [Versión 8.7.1](#release-8-7-1) | [Versión 8.7.2](#release-8-7-2)
* Campaign v8.6: [Versión 8.6.1](#release-8-6-1) | [Versión 8.6.2](#release-8-6-2) | [Versión 8.6.3](#release-8-6-3)
* Campaign v8.5 - [Versión 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]

## Versión 8.7.2 {#release-8-7-2}

_3 de septiembre de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#new-8-7-2}

* **Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y ampliado. [Más información](../send/sms/sms.md).

* **Notificación push enriquecida (GA)**: ahora puede enviar notificaciones push enriquecidas. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. Con esta versión, ya está disponible un conjunto de plantillas para notificaciones push enriquecidas para sus aplicaciones de iOS y Android. [Más información](../send/rich-push-android.md).

* **Promoción de la marca**: las opciones de promoción de la marca ya están disponibles para todos los canales, incluidos SMS y correo directo. [Más información](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

### Correcciones {#fixes-8-7-2}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843 y NEO-79328.

## Versión 8.7.1 {#release-8-7-1}

_2 de mayo de 2024_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#new-8-7-1}

* **Plantillas de notificaciones push enriquecidas**: ahora puede enviar notificaciones push enriquecidas a través de Android. Las notificaciones push enriquecidas son una forma mejorada de notificación móvil que va más allá de los simples mensajes de texto al incorporar elementos multimedia como imágenes, botones interactivos u otro contenido con medios enriquecidos. [Más información](../send/rich-push-ios.md).

* **Promoción de la marca**: como usuario migrado de Campaign Standard, ahora los administradores técnicos pueden definir una o varias marcas para centralizar los parámetros que afectan a la identidad de una marca. Esto incluye el logotipo de la marca, el dominio de la URL de acceso de la página de destino o la configuración del seguimiento de mensajes. Con Adobe Campaign, puede crear estas marcas y vincularlas a mensajes o páginas de destino. Esta configuración se administra en plantillas. [Más información](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

* **API de REST**: como usuario migrado de Campaign Standard, puede utilizar las API de REST para crear integraciones para Adobe Campaign y generar su propio ecosistema interconectando Adobe Campaign con el panel de tecnologías que emplea. [Más información](../dev/api/get-started-apis.md)

* **Creación de informes dinámicos**: como usuario migrado de Campaign Standard, puede acceder a la Creación de informes dinámicos, que proporciona informes totalmente personalizables y en tiempo real para medir el impacto de sus actividades de marketing. Añade acceso a los datos de perfil, lo que permite el análisis demográfico por dimensiones de perfil como género, ciudad y edad, además de datos funcionales de campaña de correo electrónico como aperturas y clics. [Más información](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

### Actualizaciones de compatibilidad {#comp-8-7-1}

Se han añadido los siguientes conectores FDA. Consulte [esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks ahora se admite como base de datos externa con acceso de datos federado (FDA) de Adobe Campaign.

* Ya está disponible el nuevo conector ODBC de Amazon Redshift FDA. Ofrece una conectividad mejorada, un mantenimiento más sencillo y una compatibilidad mejorada. Esta nueva versión incorpora las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC, que se alinea con los conectores FDA más recientes. Esto garantiza una asistencia a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos mediante compartimentos s3, lo que mejora significativamente el rendimiento.

  El conector heredado aún se puede utilizar. Si desea probar el nuevo, póngase en contacto con su representante de Adobe.

### Migración a la credencial OAuth de servidor a servidor {#change-8-7-1}

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. Adobe realizará la migración de JWT a OAuth para sus integraciones de salida, como la integración de Campaign-Analytics o la integración de Activadores de Experience Cloud.

Si ha implementado integraciones entrantes con Campaign, debe migrar su cuenta técnica como se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio existente (JWT) seguirán funcionando hasta el **martes, 30 de junio de 2025**.

### Mejoras generales {#improvements-8-7-1}

* Se han cambiado varios esquemas de 32 a 64 bits. Esto solo se aplica a los clientes que migran de Campaign Standard. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=es){target="_blank"}

* En las tablas de Campaign, los siguientes atributos ahora se rellenan de forma predeterminada por la fecha y la hora del servidor: `lastModified` y `created`. El valor del atributo `createdBy-id` ahora se rellena con el ID de inicio de sesión actual de forma predeterminada. Los valores proporcionados por los usuarios en las llamadas de API se ignoran. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS se admite ahora para llamadas de API externas.

### Correcciones {#fixes-8-7-1}

En esta versión se han solucionado los siguientes problemas:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054



## Versión 8.6.3 {#release-8-6-3}

_30 de julio de 2024_

### Nuevas funciones {#new-8-6-3}

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


## Actualizaciones de mayo de 2024 {#may-updates}

El siguiente cambio se publicó en mayo y ahora está disponible para los usuarios de Campaign v8:

* **Nuevo complemento de seguridad mejorada**: para hacer que la conexión de red sea más segura y proporcionar una seguridad mejorada para sus recursos, Adobe Campaign ofrece un nuevo complemento de seguridad mejorada, que incluye dos funciones: integración CMK segura y túnel VPN seguro. [Más información](../config/enhanced-security.md)

## Versión 8.6.2 {#release-8-6-2}

_23 de febrero de 2024_

### Correcciones {#fixes-8-6-2}

Esta versión corrige el siguiente problema:

* Se ha corregido un problema de rendimiento que podría producirse en la instancia de intermediario (NEO-72595).

## Versión 8.6.1 {#release-8-6-1}

_14 de febrero de 2024_

### Nuevas características {#new-8-6-1}

* A partir de esta versión, tendrá acceso a la nueva **Interfaz de usuario web de Campaign**, disponible a través del entorno central de Adobe Experience Cloud. Experience Cloud es la familia integrada de aplicaciones, productos y servicios de marketing digital de Adobe. Desde su intuitiva interfaz, puede acceder rápidamente a sus aplicaciones, funciones de productos y servicios en la nube. Obtenga información sobre cómo conectarse a Adobe Experience Cloud y acceder a la interfaz de Adobe Campaign Web [en esta página](campaign-ui.md#ac-web-ui).

  >[!AVAILABILITY]
  >
  >La interfaz de usuario web de Campaign solo está disponible para los usuarios que se conectan a Adobe Campaign con su Adobe ID. Obtenga más información sobre el [sistema de administración de identidades (IMS) de Adobe](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.
  >

* Adobe Campaign v8 ahora se integra con **Adobe Experience Manager as a Cloud Service**, con la creación exclusivamente disponible a través de la interfaz de usuario web de Adobe Campaign. [Más información](../connect/ac-aem.md)

* Ahora puede utilizar su **Biblioteca de recursos de Adobe Experience Manager** junto con los recursos de su Experience Cloud, incluso si el paquete Integración con Adobe Experience Cloud está instalado en la instancia de Adobe Campaign. [Más información](../connect/ac-aem.md#assets-library)

### Mejoras generales {#improvements-8-6-1}

* Campaign v8.6 ofrece un rendimiento mejorado para **indicadores de seguimiento de envíos de correo electrónico**. Con nuestros procesos optimizados, el seguimiento de la ingesta y el tiempo de cálculo se reducen, y puede comprobar los indicadores clave de envío mucho más rápido.


### Actualizaciones de la entregabilidad {#deliverability-8-6-1}

* En febrero de 2024, cualquier compañía que envíe más de 5000 mensajes de correo electrónico a través de Google o Yahoo! tendrá que empezar a utilizar una tecnología de autenticación conocida como Domain based Message Authentication, Reporting and Conformance (DMARC). Asegúrese de tener configurado el registro DMARC para todos los subdominios que utilice con Adobe Campaign. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=es){target="_blank"}

* A partir del 1 de junio de 2024, Google y Yahoo! exigirán a los remitentes que cumplan con la cancelación de la suscripción a una lista en un clic. Adobe Campaign ahora admite esta opción. [Más información](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}


### Correcciones {#fixes-8-6-1}

En esta versión se han solucionado los siguientes problemas:

NEO-67892,-67235, NEO-66797,-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973,-63879,-63815,-63657,-63539,-63294,-63174,-62686,-62455,-62406,-61580,-63387,-NEO,-62964,-62750,-NEO,-,-61199,-,-NEO,-NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO,-60786,-59544,-59198,-,-,-59059,-58637 55197 52542 50488 47789



## Versión 8.5.3 {#release-8-5-3}

_28 de mayo de 2024_

### Migración a la credencial OAuth de servidor a servidor {#change-8-5-3}

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. [Más información](#change-8-7-1)

### Correcciones {#fixes-8-5-3}

En esta versión se han solucionado los siguientes problemas:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542