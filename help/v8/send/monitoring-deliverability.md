---
product: campaign
title: Monitorización de la entregabilidad en Adobe Campaign
description: Obtenga información acerca de las herramientas y las directrices sobre la monitorización de la entregabilidad en Adobe Campaign
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 66%

---

# Monitorización de la capacidad de entrega{#monitoring-deliverability}

A continuación, encontrará detalles sobre las herramientas de monitorización que proporciona Adobe Campaign, así como algunas directrices adicionales para aprovechar las funciones que ofrece para monitorizar la capacidad de entrega de su plataforma.

## Herramientas de monitorización {#monitoring-tools}

Adobe Campaign le permite acceder a todas las herramientas de envío enumeradas a continuación.

* El [informe de procesamiento de la bandeja de entrada](inbox-rendering.md) le permite obtener una vista previa de sus mensajes en los principales clientes de correo electrónico para analizar el contenido y la reputación.

* El informe **[!UICONTROL Delivery throughput]** proporciona una visión general del rendimiento de toda la plataforma durante un período determinado. Para obtener más información, consulte [esta sección](../reporting/global-reports.md#delivery-throughput).
* Cada envío genera un informe de estadísticas de difusión para los diferentes proveedores de servicio de Internet (ISP). Muestra algunas métricas de calidad de datos y reputación que pueden afectar la capacidad de envío, incluidas las siguientes cifras:
   * **[!UICONTROL Hard bounces]** indican la calidad de los datos. Este valor debe ser inferior al 2 %.
   * **[!UICONTROL Soft bounces]** indican reputación. Este valor no debe ser superior al 10 % para un ISP determinado.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* De manera más general, el [panel de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=es#sending-messages){target="_blank"} le permite acceder a:
   * el resumen del envío, que muestra el detalle del envío y el número de mensajes que se van a enviar, procesados y enviados con éxito;
   * los registros de envío y el historial, que muestran qué destinatario se ha excluido y por qué;
   * los registros de seguimiento, que muestran información de seguimiento como aperturas y clics.

## Directrices de monitorización {#monitoring-guidelines}

Estas son algunas directrices adicionales sobre la monitorización de la capacidad de envío:

* Compruebe regularmente el [rendimiento del envío](../reporting/global-reports.md#delivery-throughput) de toda la plataforma para comprobar si es coherente con la configuración original.
* Compruebe que [los reintentos](delivery-failures.md#retries) estén correctamente configurados (30 minutos para el periodo de reintento y más de 20 reintentos) en plantillas de envíos.
* Compruebe periódicamente si puede acceder al buzón de [rechazados](delivery-failures.md#bounce-mail-qualification) y que la cuenta no esté a punto de caducar.
* Compruebe el rendimiento de cada envío, accesible desde [panel de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=es#sending-messages){target="_blank"}, para asegurarse de que es coherente con la validez del contenido del envío (por ejemplo, las &quot;ventas flash&quot; deben entregarse en minutos, no en días). es una herramienta clave para monitorizar las entregas y los problemas potenciales durante la entrega de mensajes.
* Cuando utilice [olas](configure-and-send.md#sending-using-multiple-waves), compruebe que cada ola tenga tiempo suficiente para finalizar antes de que se active la siguiente.
* Compruebe que las cantidades de errores y nuevas [cuarentenas](quarantines.md) sean coherentes con otros envíos.
* Consulte cuidadosamente los [registros de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=es#delivery-logs-and-history){target="_blank"} en detalle para comprobar el tipo de errores resaltados (lista de bloqueados, problemas de DNS, reglas de correo no deseado, etc.).
