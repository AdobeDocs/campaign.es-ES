---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: ff874a8e06303625b4c96f49fdf4f303b50fb908
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 17%

---

# Últimas versiones {#latest-release}

Esta Página enumera nuevas capacidades, mejoras y correcciones que vienen con Campaign últimas versiones **de v8 (consola).** Obtén más información sobre Campaign versiones, versiones y actualizaciones de [este Página](upgrades.md). Otras versiones se enumeran en la sección Anterior versiones de esta documentación.

>[!BEGINSHADEBOX]

**En este Página**

* [Versión 8.7.4](#release-8-7-4)
* [Versión 8.7.3](#release-8-7-3)
* [Versión 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Versión 8.7.4 {#release-8-7-4}

_viernes, 10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como Campaign Standard usuario la transición a Campaign v8, obtenga más información sobre este transición en [Campaign documentación](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"} de la interfaz de usuario web v8.

### Nuevas funciones {#features-8-7-4}

* **Compatibilidad** con la API de REST de SMS: la API de REST de mensajería transaccional ya está disponible para la canal de SMS. Cuando tanto correo electrónico como el teléfono móvil están presentes en la carga útil, puede utilizar el campo &quot;wishedChannel&quot; para especificar el canal. Si no se proporciona, correo electrónico se usará de forma predeterminada a menos que wishedChannel solicite explícitamente SMS.

* **Entregas** multilingües: a partir de Campaign versión de abril de la interfaz de usuario web, podrá enviar varias entregas correo electrónico en diferentes idiomas y acceder a los informes dinámicos relacionados. Esta capacidad sólo estará disponible en Adobe Campaign interfaz Web del usuario a finales de abril y requiere una actualización del servidor a Campaign v8.7.4.

### Correcciones {#fixes-8-7-4}

En esta versión se han solucionado los siguientes problemas:

NEO-80245, NEO-83559

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* Campaign estabilidad aplicación se ha mejorado durante envío análisis en el contexto de una [implementación](../../v8/architecture/enterprise-deployment.md) empresarial (FFDA).
* Esta versión incluye mecanismos de arquitectura FFDA mejorados y reforzados, que incluyen gestión de claves, puesta en escena y replicación de datos.
* Nuevo se han introducido flujos de trabajo técnicos para la [implementación](../../v8/architecture/enterprise-deployment.md) Enterprise (FFDA). Estos flujos de trabajo replicar envío y datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujo de trabajo inicio con `Replicate nms`. [Más información](../architecture/replication.md)
* Ahora está disponible una nueva **opción Permitir que el supervisor de vigilancia mantenga flujo de trabajo funcionando permanentemente** en las propiedades flujo de trabajo. Cuando esta opción está habilitada, flujos de trabajo se reinicia automáticamente después de que se produce un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue siendo de error. Para ajustar este intervalo, puede crear una nueva `XtkWorkflow_WatchdogRestartTimerTimeout` opción y establecer un tipo de datos Integer para especificar el nuevo retardo. Esta opción solo debe activarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones y aplicaciones de Adobe a través de la cuenta externa de **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

Se han añadido los siguientes conectores FDA. Consulte [esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks ahora se admite como una base de datos externa con Adobe Campaign acceso de datos federado (FDA).

* Ahora está disponible un nuevo conector ODBC FDA Amazon Redshift. Ofrece conectividad mejorada, mantenimiento más fácil y compatibilidad mejorada. Esta nueva versión trae las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC que se alinea con nuestros conectores FDA más recientes. Esto garantiza un soporte a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos utilizando buckets s3, lo que mejora significativamente el rendimiento.

  El conector heredado se puede seguir utilizando. Si desea probar el nuevo, comuníquese con su representante de Adobe.

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81114, NEO-81127, NEO-81209, NEO-81223, NEO-81114, NEO-81223, NEO-81123, NEO-81123, NEO-81127, NEO-81209, NEO-81223, NEO-811123, NEO-811123, NEO-811183, NEO-81123, NEO-811123, NEO-811127, NEO-81209, NEO-81223, NEO-811183, NEO-811123, NEO-811183, NEO-81123, NEO-811183, NEO-81123, NEO-811123, NEO-811183, NEO-81209 287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

