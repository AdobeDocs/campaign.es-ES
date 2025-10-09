---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 23%

---

# Últimas versiones {#latest-release}

En esta página se indican las nuevas funciones, mejoras y correcciones que se incluyen con las **últimas versiones** de la versión 8 de Campaign (consola). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md). Otras versiones se indican en la sección Versiones anteriores de esta documentación.

## Versión 8.8.2 {#release-8-8-2}

_9 de octubre de 2025_

>[!AVAILABILITY]
>
>Esta versión está en **Disponibilidad limitada** (LA).

### Nuevas funciones {#features-8-8-2}

El **nuevo conector de envío de SMS** ya está disponible para [implementaciones de FDAC de Campaign](../architecture/enterprise-deployment.md). Consulte la [documentación detallada](../send/sms/sms.md).

Esta versión también incluye un conjunto de funcionalidades disponibles con la interfaz de usuario web de Campaign:

* [Enriquecimiento de perfil en mensajes transaccionales](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Funciones multilingües para mensajes transaccionales, notificaciones push y SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Consulte las [notas de la versión](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=es){target="_blank"} de la IU web de Campaign

### Correcciones {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Se ha corregido un problema que podría provocar un error en el flujo de trabajo de limpieza de la base de datos. (NEO-87949)
* Se ha corregido un problema en Marketing distribuido por el cual los datos de seguimiento no se registraban para los envíos de campañas de colaboración. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Se ha corregido un problema que podía impedir que la personalización en fragmentos funcionara correctamente. (NEO-88161)
* Se ha corregido un problema después de migrar al nuevo conector ODBC Redshift, que podía provocar que la actividad del flujo de trabajo Dividir fallara con errores de SQL. (NEO-87466)
* Se ha corregido un problema que podría provocar recuentos de exclusión inexactos en los flujos de trabajo. (NEO-89207)
* Se ha corregido un problema que podría provocar indicadores de clics inexactos para las notificaciones push. (NEO-89503)
* Se ha corregido un problema por el cual los registros de envío de SMS no se actualizaban correctamente, lo que impedía generar informes de estado precisos en Adobe Campaign. (NEO-88479)
* Se ha corregido un problema por el cual las comillas francesas se convertían incorrectamente a comillas inglesas en el contenido de la entrega. (NEO-89631)
* Se ha corregido un problema en el cual el servidor en tiempo real devolvía un código de respuesta incorrecto para tokens de IMS no válidos en su lugar. (NEO-87428)
* Se ha corregido un problema en el cual las estadísticas de envío de correo electrónico y SMS no se volvían a calcular completamente, lo que provocaba indicadores de éxito inexactos. (NEO-88106)
* Se ha corregido un problema con el nuevo conector de envío de SMS en el que los registros de envío asignaban incorrectamente el estado de envío a un pequeño subconjunto de mensajes. (NEO-89581)
* Se ha corregido un problema con el nuevo conector de envío de SMS en el que las métricas de éxito de los envíos de T-Mobile no se actualizaban correctamente en los servidores de marketing e intermediarios. (NEO-89850)
* Se ha corregido un problema de sincronización entre las instancias de Tiempo real y Marketing que provocaba registros de seguimiento faltantes e informes incorrectos. (NEO-90247)
* Se ha corregido un problema de enriquecimiento del flujo de trabajo que podía provocar errores al seleccionar campos en dos vínculos 1-N consecutivos en esquemas personalizados. (NEO-87682)

