---
title: Notas de la versión de Campaign v8
description: Última versión de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 20%

---

# Últimas versiones {#latest-release}

En esta página se indican las nuevas funciones, mejoras y correcciones que se incluyen con las **últimas versiones** de la versión 8 de Campaign (consola). Obtenga más información sobre las versiones y actualizaciones de Campaign en [esta página](upgrades.md). Otras versiones se indican en la sección Versiones anteriores de esta documentación.

## Versión 8.9.1 {#release-8-9-1}

_27 de enero de 2026_

>[!CAUTION]
>
> La actualización de la consola de cliente es obligatoria. Obtenga información sobre cómo actualizar la consola de cliente en esta [página](../start/connect.md#upgrade-ac-console).

### Nuevas funciones {#new-8-9-1}

El **nuevo conector de envío de SMS** ya está disponible para todos los clientes (GA). Consulte la [documentación detallada](../send/sms/sms.md).

Esta versión incorpora un conjunto de funcionalidades disponibles con la interfaz de usuario web de Campaign:

* [Funciones de envío multilingüe (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Enriquecimiento de perfil en mensajes transaccionales (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Copias de Adobe Experience Manager en vivo y de idioma](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Experimentos de contenido: pruebas A/B](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Actividad de envío continuo](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Administración de aprobación de campaña](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Consulte las [notas de la versión](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=es){target="_blank"} de la IU web de Campaign

### Mejoras de seguridad {#security-8-9-1}

* Las cuentas externas de Snowflake ahora admiten la autenticación OAuth2, lo que proporciona métodos de autenticación modernos y seguros para conexiones de acceso a datos federadas. (NEO-87013)
* Se corrigieron las vulnerabilidades de acceso a archivos de flujo de trabajo restringiendo las operaciones a directorios autorizados, evitando el acceso no autorizado y la posible ejecución de código remoto. (NEO-88460)
* Se han agregado controles de inclusión en la lista de permitidos de URL de FTP a las actividades de flujo de trabajo de código JavaScript, restringiendo las conexiones FTP salientes solo a direcciones autorizadas. (NEO-89083)

### Otros cambios {#changes-8-9-1}

* Se ha mejorado la administración de la memoria contenedora mediante la implementación de restricciones automáticas del flujo de trabajo durante condiciones de alta memoria, con capacidades inteligentes de reinicio del flujo de trabajo y protecciones de memoria para procesos no críticos. (NEO-89041)
* Se ha agregado compatibilidad con las funciones asimétricas de cifrado y descifrado en los flujos de trabajo de Campaign. (NEO-80257)
* Rendimiento mejorado del agente de replicación y resistencia de la memoria para cargas de datos grandes en implementaciones de FDAC. (NEO-88430)


### Correcciones {#fixes-8-9-1}

* Se ha corregido un problema por el cual los informes dinámicos mostraban recuentos incorrectos al agruparse por determinadas columnas. (NEO-86898)
* Se han resuelto discrepancias entre los informes dinámicos y los datos de campaña reales. (NEO-88068)
* Se han corregido problemas de concatenación con los tipos de campo &quot;char&quot; de PostgreSQL que provocaban resultados inesperados en las consultas. (NEO-87769)
* Se ha corregido un problema por el que el comando logInfo de JavaScript no gestionaba correctamente ciertos parámetros. (NEO-88263)
* Se han resuelto problemas de bloqueo de sincronización en el procesamiento de eventos en tiempo real del Centro de mensajes. (NEO-88330)
* Se ha corregido un problema en el cual el Editor visual aplicaba automáticamente un nuevo formato al contenido de HTML, lo que producía cambios de diseño. (NEO-88409)
* Se ha corregido un problema por el que la actividad Deduplicación no funcionaba correctamente con esquemas temporales. (NEO-88577)
* Se ha corregido un problema que impedía que se generaran direcciones semilla al enviar pruebas. (NEO-88720)
* Se ha mejorado el rendimiento de las consultas PostgreSQL al optimizar el control de columnas de partición. (NEO-88771)
* Se ha resuelto un problema en el cual las actividades de transferencia de archivos no gestionaban correctamente los caracteres de continuación de línea. (NEO-88812)
* Optimización de la consulta PostgreSQL mejorada para un mejor rendimiento en conjuntos de datos grandes. (NEO-88885)
* Se ha corregido el error &quot;Permiso denegado&quot; que impedía que se abrieran las campañas híbridas. (NEO-88955)
* Compatibilidad ampliada con funciones de código de barras para gestionar cadenas de texto más largas. (NEO-88958)
* Se corrigió un error en los registros de campaña que se producía al utilizar pruebas con envíos recurrentes. (NEO-88976)
* Se ha corregido un problema que afectaba a las operaciones de envío de correo electrónico en determinados escenarios. (NEO-89019)
* Se ha resuelto un problema en el cual el modo de inicio del flujo de trabajo cambiaba inesperadamente de Inmediato a Normal. (NEO-89025)
* Se han corregido errores que se producían al ejecutar la actividad Actualizar datos en condiciones específicas. (NEO-89031)
* Se ha corregido un problema en el cual la actividad Actualizar datos perdía metadatos de esquema personalizados. (NEO-89056)
* Se ha corregido un error de validación que se producía durante la preparación de la entrega. (NEO-89063)
* Se ha resuelto la generación de SQL no válido cuando las consultas contenían filtros en relaciones de vínculo 1-1. (NEO-89065)
* Se ha corregido un problema en el cual la actividad Consulta incremental no respetaba el límite de tamaño configurado. (NEO-89066)
* Rendimiento de flujo de trabajo mejorado en implementaciones de FDAC para operaciones a gran escala. (NEO-89098)
* Administración y estabilidad de memoria mejoradas para procesos de flujo de trabajo. (NEO-89105)
* Se habilitó la validación estricta de columnas para formularios web para evitar incoherencias en los datos. (NEO-89111)
* Se han resuelto problemas de sincronización del Centro de mensajes que provocaban retrasos de procesamiento. (NEO-89138)
* Se corrigieron errores en el flujo de trabajo &quot;Actualizar la entrega&quot; que impedían la ejecución adecuada. (NEO-89160)
* Se corrigieron errores que se producían al ejecutar actividades de código JavaScript en flujos de trabajo. (NEO-89169)
* Se han eliminado las configuraciones de Snowflake data warehouse codificadas para permitir una configuración correcta de cuenta externa. (NEO-89201)
* Se corrigieron 403 errores prohibidos que se producían durante las operaciones de transferencia de archivos de flujo de trabajo. (NEO-89226)
* Consultas lentas optimizadas en la tabla de destinatarios en implementaciones de FDAC. (NEO-89268)
* Se ha corregido un problema en el cual las actividades de consulta incrementales ignoraban las programaciones configuradas. (NEO-89317)
* Se han resuelto errores de acceso al abrir campañas en entornos híbridos. (NEO-89320)
* Se han corregido discrepancias en los informes de la interfaz de usuario web de Campaign en los que las estadísticas de seguimiento mostraban valores diferentes en comparación con la consola. Los informes Indicadores de seguimiento, Resumen de envío y Flujos de clic en URL ahora muestran métricas coherentes en ambas interfaces. (NEO-82339)