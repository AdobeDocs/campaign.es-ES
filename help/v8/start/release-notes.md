---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 29%

---

# Últimas versiones {#latest-release}

Esta página lista las nuevas funciones, mejoras y correcciones que se proporcionan con las últimas versiones de la versión 8 de Campaign (Console). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md).

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_


### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación Campaign se mejoró durante el análisis de envío en el contexto de una implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la duplicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`.
* Ahora hay disponible una nueva opción **Habilitar al supervisor del vigilante para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está habilitada, los flujos de trabajo se reinician automáticamente después de que se produzca un error. De forma predeterminada, el reinicio se produce cada 30 segundos. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos.

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