---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: b83222774b026348ae70f41a8193f88856af99a9
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 55%

---

# Últimas versiones {#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones incluidas en la versión 8 de Campaign (consola) **últimas versiones**. Obtenga más información acerca de las versiones, actualizaciones y publicaciones de Campaign en [esta página](upgrades.md). Otras versiones se enumeran en la sección Versiones anteriores de esta documentación.

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación Campaign se mejoró durante el análisis de envío en el contexto de una implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la duplicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`.
* Ahora hay disponible una nueva opción **Habilitar al supervisor del vigilante para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está habilitada, los flujos de trabajo se reinician automáticamente después de que se produzca un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue dando error. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones de Adobe y las aplicaciones a través de la cuenta externa **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA). Obtenga más información [en esta página](compatibility-matrix.md#FederatedDataAccessFDA).

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-83096, NEO-83081.

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