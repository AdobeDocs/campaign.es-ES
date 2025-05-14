---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6d2425f7e7f35f5461151790fbda2bef2959bff4
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 35%

---

# Últimas versiones {#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones incluidas en la versión 8 de Campaign (consola) **últimas versiones**. Obtenga más información acerca de las versiones, actualizaciones y publicaciones de Campaign en [esta página](upgrades.md). Otras versiones se enumeran en la sección Versiones anteriores de esta documentación.

>[!BEGINSHADEBOX]

**En esta página**

* [Versión 8.6.5](#release-8-6-4)
* [Versión 8.7.4](#release-8-7-4)
* [Versión 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Versión 8.6.5 {#release-8-6-5}

_sábado, 25 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión se encuentra en **Disponibilidad limitada** (LA).

### Nuevas funciones {#features-8-6-5}

**Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y ampliado. [Más información](../send/sms/sms.md).

### Mejoras generales {#improvements-8-6-5}

* Se ha mejorado el rendimiento global de la aplicación, en el contexto de una implementación empresarial (FDAC) , incluida la entrega a prueba de envíos y la limpieza de la base de datos.

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS se admite ahora para llamadas de API externas.

* Agente de transferencia de correo (MTA): se ha corregido que un elemento secundario de MTA huérfano quede bloqueado en estado **[!UICONTROL Start pending]**.

### Correcciones {#fixes-8-6-5}

En esta versión se han corregido también los siguientes problemas:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versión 8.7.4 {#release-8-7-4}

_viernes, 10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-4}

* **Compatibilidad con la API REST de SMS**: la API REST de mensajería transaccional ya está disponible para el canal SMS. Cuando el correo electrónico como el teléfono móvil están presentes en la carga útil, puede utilizar el campo &quot;wishedChannel&quot; para especificar el canal. Si no se proporciona, el correo electrónico se utilizará de forma predeterminada a menos que wishedChannel solicite explícitamente un SMS.

* **Envíos multilingües**: a partir de la versión de abril de la interfaz de usuario web de Campaign, podrá realizar varios envíos de correo electrónico en diferentes idiomas y acceder a los informes dinámicos relacionados. Esta funcionalidad solo estará disponible en la interfaz de usuario web de Adobe Campaign a finales de abril y requiere una actualización del servidor a Campaign v8.7.4.

### Correcciones {#fixes-8-7-4}

En esta versión se han solucionado los siguientes problemas:

NEO-80245, NEO-83559

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación Campaign se mejoró durante el análisis de envío en el contexto de una implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la duplicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`. [Más información](../architecture/replication.md)
* Ahora hay disponible una nueva opción **Habilitar al supervisor del vigilante para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está habilitada, los flujos de trabajo se reinician automáticamente después de que se produzca un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue dando error. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogRestartTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones y aplicaciones de Adobe a través de la cuenta externa de **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

Se han añadido los siguientes conectores FDA. Consulte [esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA).

* Ya está disponible un nuevo conector ODBC de Amazon Redshift FDA. Ofrece una conectividad mejorada, un mantenimiento más sencillo y una compatibilidad mejorada. Esta nueva versión incorpora las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC, que se alinea con los conectores FDA más recientes. Esto garantiza una asistencia a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos mediante bloques de s3, lo que mejora significativamente el rendimiento.

  El conector heredado aún se puede utilizar. Si desea probar el nuevo, póngase en contacto con su representante de Adobe.

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-48232,-67814, NEO-71388,-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986,-77162,-77452,-78946,-79373,-80314,-81209,-81287,-81290,-81312,-81512,-80243,-NEO,-81127,-NEO,-81223,-NEO, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781 NEO-, NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO NEO-82920 83081 83096 83137 83143.

