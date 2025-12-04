---
product: campaign
title: Monitorización de la entregabilidad en Adobe Campaign
description: Obtenga información acerca de las herramientas y las directrices sobre la monitorización de la entregabilidad en Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 55%

---

# Monitorización de la capacidad de entrega{#monitoring-deliverability}

A continuación, encontrará detalles sobre las herramientas de monitorización que proporciona Adobe Campaign, así como algunas directrices adicionales para aprovechar las funciones que ofrece para monitorizar la capacidad de entrega de su plataforma.

## Herramientas de monitorización {#monitoring-tools}

Adobe Campaign le permite acceder a las herramientas de envío que se enumeran a continuación.

### Procesamiento de la bandeja de entrada {#inbox-rendering-tool}

El [informe de procesamiento de la bandeja de entrada](inbox-rendering.md) le permite obtener una vista previa de sus mensajes en los principales clientes de correo electrónico para analizar el contenido y la reputación.

### Rendimiento del envío {#throughput-reports}

El informe **[!UICONTROL Delivery throughput]** proporciona una visión general del rendimiento de toda la plataforma durante un período determinado. Para obtener más información, consulte [esta sección](../reporting/global-reports.md#delivery-throughput).

### Estadísticas de difusión {#broadcast-statistics}

Cada envío genera un informe de estadísticas de difusión para los diferentes proveedores de servicio de Internet (ISP). Muestra algunas métricas de calidad de datos y reputación que pueden afectar la capacidad de envío, incluidas las siguientes cifras:

**[!UICONTROL Hard bounces]** indican la calidad de los datos. Este valor debe ser inferior al 2 %.

**[!UICONTROL Soft bounces]** indican reputación. Este valor no debe ser superior al 10 % para un ISP determinado.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Panel de control de envíos {#delivery-dashboard-monitoring}

De manera más general, el [panel de control de envío](delivery-dashboard.md) le permite acceder a:

El resumen de la entrega, que muestra el detalle de la entrega y el número de mensajes que se van a enviar, procesados y enviados con éxito.

Los registros de envío y el historial, que muestran qué destinatario se ha excluido y por qué.

Los registros de seguimiento, que muestran información de seguimiento como aperturas y clics.

### Prueba de SpamAssassin {#spam-testing}

Use [SpamAssassin](spamassassin.md) para probar el contenido del correo electrónico y puntuarlo para determinar si un mensaje corre el riesgo de que las herramientas de filtrado de correo no deseado utilizadas durante la recepción lo consideren como no deseado.

### Panel de control {#control-panel-monitoring}

>[!NOTE]
>
>El Panel de control de Campaign está disponible para los usuarios de Cloud Services administrados de Campaign v8. Más información sobre el [Panel de control](../config/self-service.md).

El [Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es){target="_blank"} de Campaign proporciona funciones de supervisión para la capacidad de entrega, incluida la administración de subdominios y certificados, la supervisión de perfiles activos y las métricas de latencia y rendimiento de entrega.

## Directrices de monitorización {#monitoring-guidelines}

Estas son algunas directrices adicionales sobre la monitorización de la capacidad de envío:

### Monitorización del rendimiento de Platform

Compruebe regularmente el [rendimiento del envío](../reporting/global-reports.md#delivery-throughput) de toda la plataforma para comprobar si es coherente con la configuración original.

### Configuración de reintento

Compruebe que [los reintentos](delivery-failures.md#retries) estén correctamente configurados (30 minutos para el periodo de reintento y más de 20 reintentos) en plantillas de envíos.

### Verificación del buzón devuelto

Compruebe periódicamente si puede acceder al buzón de [rechazados](delivery-failures.md#bounce-mail-qualification) y que la cuenta no esté a punto de caducar.

### Comprobación del rendimiento del envío

Compruebe el rendimiento de cada entrega, accesible desde el [panel de control de entrega](delivery-dashboard.md), para asegurarse de que es coherente con la validez de su contenido (por ejemplo, las “ventas flash” deben entregarse en minutos, no en días).

### Validación de temporización de ondas

Cuando utilice [olas](configure-and-send.md#sending-using-multiple-waves), compruebe que cada ola tenga tiempo suficiente para finalizar antes de que se active la siguiente.

### Supervisión de cuarentena

Compruebe que las cantidades de errores y nuevas [cuarentenas](quarantines.md) sean coherentes con otros envíos.

### Análisis del registro de envío

Consulte cuidadosamente los [registros de envío](delivery-dashboard.md#delivery-logs-and-history) en detalle para comprobar el tipo de errores resaltados (lista de bloqueados, problemas de DNS, reglas de correo no deseado, etc.).

## Temas relacionados

[La Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es){target="_blank"} proporciona instrucciones detalladas sobre la estrategia de entrega, definición, métricas y prácticas recomendadas.

[Qué es la capacidad de envío](about-deliverability.md) presenta conceptos clave sobre la capacidad de envío y cómo mejorar la tasa de envío en Campaign.

[Errores y rechazos de entrega](delivery-failures.md) describe los diferentes tipos de errores de entrega, el modo en que Campaign los gestiona e incluye instrucciones para solucionar problemas comunes.

[Administración de cuarentena](quarantines.md) explica cómo Campaign administra las direcciones en cuarentena para proteger su reputación de envío.

[Controlar el contenido del mensaje](control-message-content.md) proporciona instrucciones sobre cómo garantizar que el contenido esté optimizado para la entrega.
