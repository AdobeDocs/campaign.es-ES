---
title: Notas de la versión de la version 8 de Campaign de 2025 (consola)
description: Lista de funciones y mejoras incluidas en las versiones de Campaign v8 de 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 96%

---

# Notas de la versión de 2025 {#2025-rn}

En esta página se indican las nuevas funcionalidades, mejoras y correcciones que se incluyen con la **la versión 8 de Campaign de 2025**. Para obtener la última versión, consulte [esta página](release-notes.md).

Para cualquier implementación nueva o actualización a un entorno existente, instale [la versión más reciente](release-notes.md).

>[!BEGINSHADEBOX]

**En esta página**

* [Versión 8.6.5](#release-8-6-5)
* [Versión 8.6.4](#release-8-6-4)
* [Versión 8.7.4](#release-8-7-4)
* [Versión 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Versión 8.6.5 {#release-8-6-5}

_25 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA).

### Nuevas funciones {#features-8-6-5}

**Nuevo conector de envío de SMS**: el conector de envío de SMS se ha modernizado y mejorado para habilitar conexiones SMPP en modo transceptor, habilitar conexiones SMPP persistentes y garantizar una mejor compatibilidad para entornos que realizan la transición desde Adobe Campaign Standard. Ya está disponible una nueva cuenta externa de SMS para todas las implementaciones de SMS nuevas. Las implementaciones existentes siguen siendo compatibles, pero se recomienda pasar a este nuevo conector moderno y ampliado. [Más información](../send/sms/sms.md).

### Mejoras generales {#improvements-8-6-5}

* Se ha mejorado el rendimiento global de la aplicación, en el contexto de una implementación empresarial (FDAC), incluyendo el envío de pruebas de entrega y la limpieza de la base de datos.

* Para aumentar la seguridad de todas las comunicaciones entre aplicaciones, mTLS se admite ahora para llamadas de API externas.

* Agente de transferencia de correo (MTA): se ha corregido que un elemento secundario de MTA huérfano quede bloqueado en estado **[!UICONTROL Start pending]**.

### Correcciones {#fixes-8-6-5}

En esta versión, también se han corregido los siguientes problemas:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Versión 8.7.4 {#release-8-7-4}

_10 de abril de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-4}

* **Compatibilidad con la API REST de SMS**: la API REST de mensajería transaccional ya está disponible para el canal de SMS. Cuando el correo electrónico como el teléfono móvil están presentes en la carga útil, puede utilizar el campo “wishedChannel” para especificar el canal. Si no se proporciona, se utiliza de forma predeterminada el correo electrónico, a menos que wishedChannel solicite explícitamente un SMS.

* **Envíos multilingües**: a partir de la versión de abril de la interfaz de usuario web de Campaign, podrá realizar varios envíos de correo electrónico en diferentes idiomas y acceder a los informes dinámicos relacionados. Esta funcionalidad solo estará disponible en la interfaz de usuario web de Adobe Campaign a finales de abril y requiere una actualización del servidor a la versión 8.7.4 de Campaign.

### Correcciones {#fixes-8-7-4}

En esta versión se han solucionado los siguientes problemas:

NEO-80245, NEO-83559

## Versión 8.7.3 {#release-8-7-3}

_14 de febrero de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario de Campaign Standard que está realizando la transición a la versión 8 de Campaign, obtenga más información sobre esta transición en la [documentación de la interfaz de usuario web de la versión 8 de Campaign](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-3}

* **Informes dinámicos para mensajes transaccionales**: ahora puede supervisar los mensajes transaccionales en la interfaz de usuario de informes dinámicos. Estos informes permiten al experto en marketing ver todas las métricas y dimensiones de informes de los mensajes transaccionales, así como el desglose de envíos realizados a través de una plantilla en tiempo real. [Más información](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **API REST de mensajería transaccional**: las API transaccionales basadas en eventos ya están disponibles para los correos electrónicos. [Más información](../dev/api/get-started-apis.md)

### Correcciones {#fixes-8-7-3}

En esta versión se han solucionado los siguientes problemas:

NEO-79373, NEO-81908, NEO-83081

## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación de Campaign se ha mejorado durante el análisis del envío en el contexto de una [implementación empresarial (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la replicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la [implementación empresarial (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`. [Más información](../architecture/replication.md)
* Ahora hay disponible una nueva opción **Habilitar el supervisor de vigilancia para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está activada, los flujos de trabajo se reinician automáticamente si se produce un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue dando error. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogRestartTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones y aplicaciones de Adobe a través de la cuenta externa de **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

Se han añadido los siguientes conectores FDA. Consulte [esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks ahora se admite como base de datos externa con acceso de datos federado (FDA) de Adobe Campaign.

* Ya está disponible el nuevo conector ODBC de Amazon Redshift FDA. Ofrece una conectividad mejorada, un mantenimiento más sencillo y una compatibilidad mejorada. Esta nueva versión incorpora las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC, que se alinea con los conectores FDA más recientes. Esto garantiza una asistencia a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos mediante compartimentos s3, lo que mejora significativamente el rendimiento.

  El conector heredado aún se puede utilizar. Si desea probar el nuevo, póngase en contacto con su representante de Adobe.

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

