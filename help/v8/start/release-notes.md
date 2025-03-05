---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 15faa6850c035d2d26dd43dc221e0128c33999c2
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 21%

---

# Últimas versiones {#latest-release}

Esta página lista las nuevas funcionalidades, mejoras y correcciones incluidas en la versión 8 de Campaign (consola) **últimas versiones**. Obtenga más información acerca de las versiones, actualizaciones y publicaciones de Campaign en [esta página](upgrades.md). Otras versiones se enumeran en la sección Versiones anteriores de esta documentación.

>[!BEGINSHADEBOX]

**En esta página**

* Campaign v8.6 - [Versión 8.6.4](#release-8-6-4)
* Campaign v8.7: [Versión 8.7.3](#release-8-7-3)

>[!ENDSHADEBOX]


## Versión 8.7.3 {#release-8-7-3}

_14 de febrero de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA). Está restringido a los clientes que migran **de Adobe Campaign Standard a la versión 8 de Adobe Campaign** y no se puede implementar en ningún otro entorno.
>
>Como usuario Campaign Standard que está realizando la transición a Campaign v8, obtenga más información sobre esta transición en la [Documentación de la interfaz de usuario web de Campaign v8](https://experienceleague.adobe.com/es/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nuevas funciones {#features-8-7-3}

* **Informes dinámicos para mensajes transaccionales**: ahora puede supervisar los mensajes transaccionales en la interfaz de usuario de informes dinámicos. Estos informes permiten al experto en marketing ver todas las métricas y dimensiones de informes de los mensajes transaccionales, así como el desglose de envíos enviados a través de una plantilla en tiempo real. [Más información](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **API de REST de mensajería transaccional**: las API transaccionales basadas en eventos ya están disponibles para los correos electrónicos. [Más información](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correcciones {#fixes-8-7-3}

En esta versión se han solucionado los siguientes problemas:

NEO-79373, NEO-81908, NEO-83081


## Versión 8.6.4 {#release-8-6-4}

_15 de enero de 2025_

### Mejoras generales {#improvements-8-6-4}

* La estabilidad de la aplicación Campaign se mejoró durante el análisis de envío en el contexto de una implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md).
* Esta versión incorpora mecanismos de arquitectura de FDAC mejorados y reforzados, incluida la administración de claves, el ensayo y la duplicación de datos.
* Se han introducido nuevos flujos de trabajo técnicos para la implementación de [Enterprise (FDAC)](../../v8/architecture/enterprise-deployment.md). Estos flujos de trabajo replican el envío y los datos relacionados centralizando las solicitudes de replicación paralelas en las tablas correspondientes. Estos flujos de trabajo comienzan con `Replicate nms`. [Más información](../architecture/replication.md)
* Ahora hay disponible una nueva opción **Habilitar al supervisor del vigilante para mantener el flujo de trabajo en ejecución de forma permanente** en las propiedades del flujo de trabajo. Cuando esta opción está habilitada, los flujos de trabajo se reinician automáticamente después de que se produzca un error. De forma predeterminada, el reinicio se produce cada 30 segundos si el flujo de trabajo sigue dando error. Para ajustar este intervalo, puede crear una nueva opción `XtkWorkflow_WatchdogTimerTimeout` y establecer un tipo de datos Integer para especificar el nuevo retraso. Esta opción solo debe habilitarse en flujos de trabajo técnicos. [Más información](../../automation/workflow/workflow-properties.md#execution)

### Mejoras de seguridad {#security-8-6-4}

La conexión con las soluciones y aplicaciones de Adobe a través de la cuenta externa **[!UICONTROL Adobe Experience Cloud]** se ha actualizado para reforzar la seguridad.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Actualizaciones de compatibilidad {#comp-8-6-4}

* Databricks ahora se admite como base de datos externa con acceso de datos federado de Adobe Campaign (FDA). Obtenga más información [en esta página](compatibility-matrix.md#FederatedDataAccessFDA).

* Ya está disponible un nuevo conector ODBC de Amazon Redshift FDA. Ofrece una conectividad mejorada, un mantenimiento más sencillo y una compatibilidad mejorada. Esta nueva versión incorpora las siguientes mejoras:

   * El nuevo conector se basa en la interfaz ODBC, que se alinea con los conectores FDA más recientes. Esto garantiza una asistencia a largo plazo.
   * También introduce un nuevo mecanismo de carga de datos mediante bloques de s3, lo que mejora significativamente el rendimiento.
   * Se ha añadido la compatibilidad con Redshift Spectrum.

  El conector heredado aún se puede utilizar. Si desea probar el nuevo, póngase en contacto con su representante de Adobe.

### Correcciones {#fixes-8-6-4}

En esta versión se han solucionado los siguientes problemas:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-81127, NEO-80314, NEO-81209, NEO-81312, NEO-81223, NEO-81287, NEO-81290, NEO-81512, NEO-O, NEO-81520, NEO-81566, NEO-80243, NEO-81704, NEO-81908, NEO-82195 NEO-, NEO O-, NEO O-, NEO O-82591, NEO O-82592, NEO O-, NEO O-, NEO O-, NEO O-82640 82665 82781 82920 83081 83096 83137 83143, NEO O-.

