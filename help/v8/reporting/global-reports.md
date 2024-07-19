---
title: Informes globales de Adobe Campaign
description: Obtenga información sobre cómo acceder y utilizar informes globales
feature: Reporting, Monitoring
role: User, Data Engineer
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1750'
ht-degree: 96%

---

# Informes globales {#global-reports}

Estos informes hacen referencia a la actividad de los datos de toda la base de datos. Para ver el tablero de informes, vaya a la pestaña **[!UICONTROL Reports]**.

![](assets/reports-tab.png)

Para mostrar los informes, haga clic en el nombre de cada uno. Los siguientes informes están disponibles de forma predeterminada:

![](assets/report-global-list.png)

>[!NOTE]
>
>Esta sección muestra solamente los informes vinculados a las entregas.

* **[!UICONTROL Delivery throughput]**: consulte [Rendimiento de entrega](#delivery-throughput).
* **[!UICONTROL Browsers]**: consulte [Navegadores](#browsers).
* **[!UICONTROL Sharing to social networks]**: consulte [Difusión en redes sociales](#sharing-to-social-networks).
* **[!UICONTROL Statistics on sharing activities]**: consulte [Estadísticas sobre actividades de uso compartido](#statistics-on-sharing-activities).
* **[!UICONTROL Operating systems]**: consulte [Sistemas operativos](#operating-systems).
* **[!UICONTROL URLs and click streams]**: consulte [Direcciones URL y flujos de clics](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Tracking indicators]**: consulte [Seguimiento de indicadores](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-deliverables and bounces]**: consulte [No entregables y devoluciones](#non-deliverables-and-bounces).
* **[!UICONTROL User activities]**: consulte [Actividades de usuario](#user-activities).
* **[!UICONTROL Subscription tracking]**: consulte [Seguimiento de suscripciones](#subscription-tracking).
* **[!UICONTROL Delivery summary]**: consulte [Resumen de entregas](delivery-reports.md#delivery-summary).
* **[!UICONTROL Delivery statistics]**: consulte las [Estadísticas de entrega](#delivery-statistics).
* **[!UICONTROL Breakdown of opens]**: consulte [Desglose de aperturas](#breakdown-of-opens).

## Rendimiento de la entrega {#delivery-throughput}

Este informe contiene información sobre el rendimiento de entrega de toda la plataforma durante un periodo determinado. Para medir la velocidad a la que se envían los mensajes, los criterios son la cantidad de mensajes enviados por hora y el tamaño de los mensajes (en bits por segundo). En el siguiente ejemplo, el primer gráfico muestra las entregas correctas en azul y la cantidad de entregas incorrectas en naranja.

![](assets/report-toolbar.png)

Se pueden configurar los valores que se muestran cambiando la escala temporal: vista de 1 hora, de 3 horas, de 24 horas, etc. Haga clic en **[!UICONTROL Refresh]** para confirmar la selección.

>[!NOTE]
>
>También puede monitorizar el número de entregas enviadas por hora usando el [Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html?lang=es){target="_blank"}.
>
>Todos los usuarios administradores pueden acceder al Panel de control. Los pasos para otorgar acceso de administrador a un usuario se detallan en [esta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=es#discover-control-panel){target="_blank"}.
>

## Actividades del usuario {#user-activities}

Este informe muestra el desglose de aperturas, clics y transacciones por media hora, hora o día, en forma de gráfico.

Estas son las opciones disponibles:

* **[!UICONTROL Opens]**: Cantidad total de mensajes abiertos. No se tienen en cuenta los correos electrónicos en formato de texto. [Más información](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : Número total de clics en los vínculos de los envíos. No se tienen en cuenta los clics en los vínculos de baja de suscripción ni en las páginas espejo.
<!--
* **[!UICONTROL Transactions]** : Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Rechazos y no entregables {#non-deliverables-and-bounces}

Este informe muestra el desglose de no entregables, así como un desglose de rechazos por dominio de Internet.

**[!UICONTROL Number of messages processed]** representa el número total de mensajes procesados por el servidor de entrega. Este valor es inferior al número de mensajes que se desea enviar cuando se han detenido o pausado algunas entregas (antes de que el servidor los procese).

**[!UICONTROL Breakdown of errors by type]**

>[!NOTE]
>
>Los errores que se muestran en este informe activan el proceso de cuarentena. Para obtener más información sobre la administración de la cuarentena, consulte [Administración de cuarentena](../send/quarantines.md).

La primera sección de este informe muestra el desglose de no entregables en forma de tabla de valores y de gráfico.

Para cada tipo de error, se cuenta con:

* el número de mensajes de error de este tipo,
* el porcentaje de mensajes con errores de este tipo comparado con el número total de mensajes con errores,
* el porcentaje de mensajes de error de este tipo comparado con el número total de mensajes procesados.

Se utilizan los siguientes indicadores:

* **[!UICONTROL User unknown]** : Tipo de error generado durante el envío para indicar que la dirección de correo electrónico no es válida.
* **[!UICONTROL Invalid domain]** : Tipo de error generado al realizar un envío para indicar que el dominio de la dirección de correo electrónico es incorrecto o no existe.
* **[!UICONTROL Inbox full]** : Tipo de error generado después de cinco intentos de envío para indicar que la bandeja de entrada de los destinatarios contiene demasiados mensajes.
* **[!UICONTROL Account disabled]** : Tipo de error generado al realizar un envío para indicar que la dirección ya no existe.
* **[!UICONTROL Rejected]** : Tipo de error generado cuando el IAP (Proveedor de acceso a Internet) rechaza una dirección, por ejemplo, al aplicar una regla de seguridad (software contra correo no deseado).
* **[!UICONTROL Unreachable]** : Tipo de error que se produce en la cadena de distribución de mensajes: incidente en la retransmisión SMTP, dominio temporalmente inaccesible, etc.
* **[!UICONTROL Not connected]** : Tipo de error que indica que el teléfono móvil de los destinatarios está apagado o desconectado de la red en el momento del envío.

  >[!NOTE]
  >
  >Este indicador se relaciona únicamente con las entregas de [canales móviles](../send/send.md).

  Se pueden abrir todas las líneas de la tabla de valores haciendo clic en el símbolo `[+]`. Para cada tipo de error, se puede mostrar el desglose de mensajes de error por dominio.

**[!UICONTROL Breakdown of errors per domain]**

La segunda sección de este informe muestra el desglose de errores por dominio de Internet en forma de tabla de valores y de un gráfico.

Para cada nombre de dominio, se muestra:

* el número de mensajes con errores para este dominio,
* el porcentaje de mensajes con errores para este dominio comparado con el número total de mensajes procesados para este dominio,
* el porcentaje de mensajes de error para este dominio comparado con el número total de mensajes de error.

Se pueden abrir todas las líneas de la tabla de valores haciendo clic en el símbolo [+]. Para cada tipo de dominio, se puede mostrar el desglose de mensajes de error por tipo de error.

![](assets/errors-report-details.png)

>[!NOTE]
>
>Los nombres de dominio mostrados en este informe se definen al nivel de cubo. Para cambiar estos valores, edite el cubo **[!UICONTROL Delivery logs (broadlogrcp)]**. Para obtener más información, consulte [esta sección](gs-cubes.md). La categoría **[!UICONTROL Others]** incluye nombres de dominio que no pertenecen a una clase específica.

## Navegadores {#browsers}

Este informe muestra el desglose de los navegadores de Internet que utilizan los destinatarios de la entrega durante el periodo correspondiente.

>[!NOTE]
>
>Los valores que se muestran en este informe son estimaciones: solo se tienen en cuenta los destinatarios que han hecho clic en una entrega.

**Estadísticas globales**

Las estadísticas globales de uso del navegador se presentan en forma de una tabla de valores y de un gráfico.

![](assets/browser-report.png)

Se utilizan los siguientes indicadores:

* **[!UICONTROL Visitors]** : Número total de destinatarios objetivo (por navegador de Internet) y que han hecho clic en un envío al menos una vez.
* **[!UICONTROL Pages viewed]** : Número total de clics en los vínculos de un envío (por navegador de Internet) para todos los envíos.
* **[!UICONTROL Usage rate]** : Esta tasa representa el desglose de los visitantes (por navegador de Internet) en relación con la cantidad total de visitantes.

**Estadísticas por navegador**

En la tabla de valores de estadísticas globales, se puede hacer clic en el nombre de cada navegador para ver sus estadísticas de uso.

![](assets/browser-report-info.png)

Las estadísticas se presentan en forma de una curva, un gráfico y una tabla de valores.

La curva **[!UICONTROL History]** representa la tasa de asistencia de este explorador por día. La tasa es la relación entre la cantidad de visitantes por día (en este navegador) comparada con el número de visitantes medidos en el día con la tasa de asistencia más alta.

El gráfico **[!UICONTROL Breakdown per version]** representa el desglose de visitantes por versión comparado con la cantidad total de visitantes (en este explorador).

La tabla de valores utiliza los indicadores siguientes:

* **[!UICONTROL Global rate]** : Esta tasa representa el desglose de visitantes por versión comparado con la cantidad total de visitantes (en todos los navegadores).
* **[!UICONTROL Relative rate]** : Esta tasa representa el desglose de visitantes por versión comparado con la cantidad total de visitantes (en este navegador).


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]** : Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]** : Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]** : Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]** : This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]** : Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]** : This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]** : This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]** : Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form. 
* **[!UICONTROL Opens]** : Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]** : Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Sistemas operativos {#operating-systems}

Este informe muestra el desglose de los sistemas operativos utilizados los destinatarios de la entrega durante el periodo correspondiente.

>[!NOTE]
>
>Los valores que se muestran en este informe son estimaciones: solo se tienen en cuenta los destinatarios que han hecho clic en una entrega.

**Estadísticas globales**

Las estadísticas de uso global de los sistemas operativos se presentan en forma de una tabla de valores y de un gráfico.

![](assets/os-report.png)

Se utilizan los siguientes indicadores:

* **[!UICONTROL Visitors]** : Promedio diario del número total de destinatarios objetivo (por sistema operativo) que hicieron clic en un envío al menos una vez.
* **[!UICONTROL Pages viewed]** : Promedio diario del número total de clics en los vínculos de envío (por sistema operativo) para todos los envíos.
* **[!UICONTROL Rate of use]** : Esta tasa representa el desglose de visitantes (por sistema operativo) en relación con el número total de visitantes.

**Estadísticas por sistema operativo**

En la tabla de valores de estadísticas globales, haga clic en el nombre de cada sistema operativo para ver las estadísticas por sistema operativo.

![](assets/os-report-details.png)

Las estadísticas se presentan en forma de una curva, un gráfico y una tabla de valores.

La curva **[!UICONTROL History]** representa la tasa de uso de este sistema operativo por día. Esta tasa es la relación entre el número de visitantes por día (en este sistema operativo) en relación con el número de visitantes medidos en el día con la mayor asistencia.

El gráfico **[!UICONTROL Breakdown by version]** representa el desglose de visitantes por versión en relación con la cantidad total de visitantes en este sistema operativo.

La tabla de valores utiliza los indicadores siguientes:

* **[!UICONTROL Global rate]** : Esta tasa representa el desglose de visitantes (por versión) en relación con la cantidad total de visitantes a través de los sistemas operativos.
* **[!UICONTROL Relative rate]** : Esta tasa representa el desglose de visitantes (por versión) en relación con la cantidad total de visitantes para este sistema operativo.

## Seguimiento de suscripciones {#subscription-tracking}

Este informe permite monitorizar las suscripciones a los servicios de información. Muestra las suscripciones y bajas de suscripción.

![](assets/service-report.png)

Se puede visualizar para una suscripción haciendo clic en el nodo **[!UICONTROL Profiles and targets > Services and subscriptions]** de la página principal o de Explorer. Seleccione la suscripción deseada y, a continuación, haga clic en la pestaña **[!UICONTROL Reports]**. El informe **[!UICONTROL Subscriptions tracking]** está disponible de forma predeterminada. Permite ver las tendencias de suscripción y de bajas de suscripción y la tasa de fidelidad durante un periodo. Se puede configurar la representación de estos datos a través de la lista desplegable. Haga clic en **[!UICONTROL Refresh]** para validar la configuración seleccionada.

Para obtener más información, consulte [esta página](../start/subscriptions.md).

**[!UICONTROL Number subscribed to date]** representa el número total de personas suscritas actualmente.

**[!UICONTROL Overall evolution of subscriptions]**

La tabla de valores utiliza los indicadores siguientes:

* **[!UICONTROL Subscribers]** : Número total de suscriptores durante el periodo correspondiente.
* **[!UICONTROL Subscriptions]** : Número de suscripciones durante el periodo correspondiente.
* **[!UICONTROL Unsubscriptions]** : Número de bajas de suscripción durante el periodo correspondiente.
* **[!UICONTROL Evolution]** : Número de bajas de suscripción menos el número de suscripciones. La tasa se calcula en función del número total de suscriptores.
* **[!UICONTROL Loyalty]** : Tasa de fidelidad de los suscriptores durante el periodo correspondiente.

**[!UICONTROL Subscription evolution curves]**

Este gráfico muestra la evolución de las suscripciones y las bajas de suscripción durante el periodo correspondiente.

## Estadísticas de envío {#delivery-statistics}

Este informe muestra el desglose por dominio de Internet, de todos los mensajes procesados y enviados, de los rechazos graves o leves, aperturas, clics y bajas de suscripción.

![](assets/broadcast-report.png)

Se utilizan los siguientes indicadores:

* **[!UICONTROL Emails processed]** : Número total de mensajes que procesa el servidor de envío.
* **[!UICONTROL Delivered]** : porcentaje del número de mensajes procesados correctamente comparado con el número total de mensajes procesados.
* **[!UICONTROL Hard bounces]** : porcentaje del número de rechazos “graves” comparado con el número total de mensajes procesados.
* **[!UICONTROL Soft bounces]** : porcentaje del número de rechazos “leves” comparado con el número total de mensajes procesados.

  >[!NOTE]
  >
  >Para obtener más información sobre las devoluciones suaves y duras, consulte [esta página](../send/quarantines.md).

* **[!UICONTROL Opens]** : porcentaje del número de destinatarios objetivo que abrieron un mensaje al menos una vez comparado con el número de mensajes procesados correctamente.
* **[!UICONTROL Clicks]** : porcentaje del número de personas que hizo clic en un envío al menos una vez comparado con el número de mensajes procesados correctamente.
* **[!UICONTROL Unsubscription]** : porcentaje del número de clics en un vínculo de baja de suscripción comparado con el número de mensajes procesados correctamente.

## Desglose de aperturas {#breakdown-of-opens}

Este informe muestra el desglose de aperturas por sistema operativo, dispositivo y navegador durante el periodo correspondiente. Para cada categoría se utilizan dos gráficos. El primero muestra estadísticas relacionadas con las aperturas en un ordenador y en dispositivos móviles. El segundo muestra estadísticas relacionadas únicamente con las aperturas en dispositivos móviles.

El número de aperturas corresponde al número total de mensajes abiertos. No se cuentan los correos electrónicos de formato de texto. Para obtener más información sobre el seguimiento de las aperturas, consulte [esta sección](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>Los nombres explorador y sistema operativo forman parte de la información que envía el agente de usuario del explorador en el que se ha abierto el mensaje. Adobe Campaign deduce el tipo de dispositivo mediante la información del dispositivo.
