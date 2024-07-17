---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 09b8ced170ff28b24713722e0a82852038053201
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 89%

---

# Últimas versiones {#latest-release}

Adobe Campaign se actualiza periódicamente. Esta frecuencia regular de actualizaciones tiene como objetivo ofrecerle lo más novedoso y lo mejor, mantener el entorno seguro y mejorar su experiencia con nuestro producto. Adobe recomienda encarecidamente a todos sus clientes que actualicen a la versión más reciente. Esta página lista las nuevas funciones, mejoras y correcciones que se proporcionan con las últimas versiones de Campaign v8 (Console). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md).

Como usuario de Cloud Services administrados, su instancia se actualiza en Adobe con cada nueva versión. Adobe se pondrá en contacto con usted y actualizará sus entornos. La consola cliente de Campaign **debe actualizarse a la misma versión** como servidores de Campaign. Obtenga información sobre cómo actualizar la consola del cliente en [esta página](../start/connect.md#upgrade-ac-console).

Además, como cliente, asegúrese de que utiliza la última versión compatible de los sistemas que se enumeran en la [Matriz de compatibilidad](compatibility-matrix.md).

## Versión 8.5.3 {#release-8-5-3}

_28 de mayo de 2024_

### Migración a la credencial OAuth de servidor a servidor {#change-8-5-3}

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. [Más información](#change-8-7-1)

### Correcciones {#fixes-8-5-3}

En esta versión se han solucionado los siguientes problemas:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## Actualizaciones de mayo {#may-updates}

El siguiente cambio se publicó en mayo y ahora está disponible para los usuarios de Campaign v8:

* **Nuevo complemento de seguridad mejorada**: para hacer que la conexión de red sea más segura y proporcionar una seguridad mejorada para sus recursos, Adobe Campaign ofrece un nuevo complemento de seguridad mejorada, que incluye dos funciones: integración CMK segura y túnel VPN seguro. [Más información](../config/enhanced-security.md)


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




### Actualizaciones de compatibilidad {#comp-8-7-1}

* Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA). Obtenga más información [en esta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Migración a la credencial OAuth de servidor a servidor {#change-8-7-1}

A partir de esta versión, y habiendo declarado Adobe la credencial Cuenta de servicio (JWT) como obsoleta, las integraciones de salida de Campaign con aplicaciones y soluciones de Adobe ahora dependen de la credencial OAuth de servidor a servidor. Adobe realizará la migración de JWT a OAuth para sus integraciones de salida, como la integración de Campaign-Analytics o la integración de Activadores de Experience Cloud.

Si ha implementado integraciones de entrada con Campaign, debe migrar su cuenta técnica como se detalla en [esta documentación](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Las credenciales de la cuenta de servicio (JWT) existentes seguirán funcionando hasta el **27 de enero de 2025**.


### Mejoras generales {#improvements-8-7-1}

* Se han cambiado varios esquemas de 32 a 64 bits. Esto solo se aplica a los clientes que migran de Campaign Standard. [Más información](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=es){target="_blank"}

* En las tablas de Campaign, los siguientes atributos ahora se rellenan de forma predeterminada por la fecha y la hora del servidor: `lastModified` y `created`. El valor del atributo `createdBy-id` ahora se rellena con el ID de inicio de sesión actual de forma predeterminada. Los valores proporcionados por los usuarios en las llamadas de API se ignoran. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS ahora se admite para llamadas de API externas.


### Correcciones {#fixes-8-7-1}

En esta versión se han solucionado los siguientes problemas:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-O, NEO-60192, NEO-58596, NEO-58314, NEO-65633, NEO-58004, NEO-40054, NEO-, NEO-, NEO, NEO-O,-O, O,-O,-O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O, O,,,,,,,,,,,, Y
