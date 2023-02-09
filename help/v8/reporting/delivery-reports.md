---
title: Informes de envío integrados de Adobe Campaign
description: Informes de envío integrados de Adobe Campaign
feature: Reporting
exl-id: e9031d65-6e0e-49da-9990-7687d2a77591
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 92%

---

# Informes de envío {#delivery-reports}

Se puede realizar un seguimiento de la ejecución de los envíos a través de diversos informes accesibles desde la información general de entrega.

Para acceder a los informes, siga los pasos a continuación:

1. Vaya a la **[!UICONTROL Campaigns]** y haga clic en **[!UICONTROL Delivery]** para mostrar la lista de envíos.
1. Haga clic en el nombre de la entrega a la que desea acceder a los informes.
1. Seleccione la pestaña **[!UICONTROL Summary]** y haga clic en el vínculo **[!UICONTROL Reports]** para acceder a los informes específicos de la entrega.

   ![](assets/detailed-report-2.png)

   De manera predeterminada, están disponibles los siguientes informes:

   * **[!UICONTROL Delivery throughput]**
   * **[!UICONTROL Sharing to social networks]**
   * **[!UICONTROL Statistics on sharing activities]**
   * **[!UICONTROL Hot clicks]**
   * **[!UICONTROL Tracking statistics]**
   * **[!UICONTROL URLs and click streams]**
   * **[!UICONTROL Tracking indicators]**
   * **[!UICONTROL Non-deliverables and bounces]**
   * **[!UICONTROL User activities]**
   * **[!UICONTROL Delivery summary]**
   * **[!UICONTROL Subscription tracking]**
   * **[!UICONTROL Delivery statistics]**
   * **[!UICONTROL Breakdown of opens]**

## Indicadores de seguimiento {#tracking-indicators}

Este informe combina los indicadores clave para realizar un seguimiento del comportamiento de los destinatarios al recibir la entrega. Permite el acceso a las estadísticas de entrega y recepción, las tasas de apertura y clics, los flujos de clics generados, el seguimiento web y las actividades de uso compartido en redes sociales.

>[!NOTE]
>
>Los valores calculados en función de los mensajes abiertos siempre son estimaciones, debido al margen de error vinculado a los correos electrónicos en formato de texto. Los indicadores **[!UICONTROL Distinct opens/Sum of opens for the population reached]** tienen en cuenta este margen de error. [Más información](metrics-calculation.md#tracking-opens-).

![](assets/tracking-report-synthesis.png)

**[!UICONTROL 1. Delivery statistics]**

* **[!UICONTROL Messages to deliver]** : Número total de mensajes que desea enviar después del análisis de envío.
* **[!UICONTROL Success]** : número de mensajes procesados correctamente.

**[!UICONTROL 2. Reception statistics]**

>[!NOTE]
>
>Los porcentajes relacionados se calculan según el número de mensajes reenviados correctamente.

* **[!UICONTROL Distinct opens for the population reached]** : Estimación del número de destinatarios objetivo que han abierto un mensaje al menos una vez. Se tienen en cuenta los clics en direcciones URL rastreadas, ya que es necesario abrir los correos electrónicos para hacer clic en un vínculo.
* **[!UICONTROL Sum of opens for the population reached]** : Estimación del número total de aperturas de los destinatarios objetivo.
* **[!UICONTROL Clicks on opt-out link]** : Número de clics en el vínculo de baja de suscripción.
* **[!UICONTROL Clicks on the mirror page link]** : Número de clics en el vínculo de página espejo. Para que se tenga en cuenta un vínculo, este debe definirse como tal en el asistente de envíos (direcciones URL rastreadas). <!--Refer to this [page](../../delivery/using/about-delivery-monitoring.md).-->
* **[!UICONTROL Estimation of forwards]** : Estimación del número de correos electrónicos reenviados por los destinatarios objetivo. Este valor se calcula restando el número de personas diferentes y el número de destinatarios diferentes que hicieron clic en el correo electrónico.

   >[!NOTE]
   >
   >Para obtener más información sobre la diferencia entre personas diferentes y destinatarios objetivo, consulte [Personas / destinatarios objetivo](metrics-calculation.md#targeted-persons---recipients).

**[!UICONTROL 3. Open and click-through rate]**

Esta tabla de valores muestra el desglose de envíos, aperturas, clics y reacciones sin procesar por dominio de Internet. Se utilizan los siguientes indicadores:

* **[!UICONTROL Sent]** : número total de mensajes enviados en este dominio.
* **[!UICONTROL Complaints]** : número de mensajes de este dominio que el destinatario ha notificado como no deseados. La tasa se calcula en función del número total de mensajes enviados en este dominio.
* **[!UICONTROL Opens]** : número de destinatarios objetivo diferentes para este dominio que han abierto un mensaje al menos una vez. La tasa se calcula en función del número total de mensajes enviados en este dominio.
* **[!UICONTROL Clicks]** : número de destinatarios objetivo diferentes que hicieron clic en el mismo entrega al menos una vez. La tasa se calcula en función del número total de mensajes enviados en este dominio
* **[!UICONTROL Raw reactivity]** : porcentaje del número de destinatarios que hicieron clic en una entrega al menos una vez comparado con el número de destinatarios que abrieron una entrega al menos una vez.

>[!NOTE]
>
>Los nombres de dominio mostrados en este informe se definen en la lista desglosada utilizada al nivel de cubo. Para cambiar, añadir o quitar dominios predeterminados, edite la lista desglosada **[!UICONTROL Domains]** y modifique los valores y alias. La categoría **[!UICONTROL Others]** incluye nombres de dominio que no pertenecen a ningún valor de la lista desglosada.
>
>Obtenga información sobre cómo acceder y configurar las enumeraciones en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target="_blank"}.


**[!UICONTROL 4. Generated click streams]**

>[!NOTE]
>
>Los porcentajes relacionados se calculan según el número de mensajes reenviados correctamente.

* **[!UICONTROL Distinct clicks for the population reached]** : Número de personas diferentes que han hecho clic en un envío al menos una vez.
* **[!UICONTROL Cumulated clicks]** : número total de clics de los destinatarios objetivo, sin contar los vínculos de baja de suscripción y las páginas espejo.
* **[!UICONTROL Recipient clicks]** : número de destinatarios objetivo diferentes que hicieron clic en el mismo entrega al menos una vez.
* **[!UICONTROL Estimated recipient reactivity]** : proporción del número de destinatarios que han hecho clic al menos una vez en una entrega en comparación con el número estimado de destinatarios que han abierto una entrega al menos una vez. No se tienen en cuenta los clics en los vínculos de exclusión ni de la página espejo.
<!--
**[!UICONTROL 5. Web tracking]**

* **[!UICONTROL Visited pages]** : Number of web pages visited following message reception.
* **[!UICONTROL Transactions]** : Number of purchases following message reception.
* **[!UICONTROL Total amount]** : Total amount of purchases following message reception. 
* **[!UICONTROL Average transaction amount]** : Average purchase made by distinct delivery recipients. 
* **[!UICONTROL Articles]** : Number of articles purchased by the delivery recipients. 
* **[!UICONTROL Average count of articles per transaction]** : Average number of items per purchase made by distinct recipients.
* **[!UICONTROL Average amount per message]** : Average amount of purchases generated per message.

  >[!NOTE]
  >
  >In order for a visited page, transaction, amount or article to be taken into account, a webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).

**[!UICONTROL 6. Sharing activities to email and social networks]**

This section shows the number of messages shared on each social network. For more on this, refer to [Sharing to social networks](../../reporting/using/global-reports.md#sharing-to-social-networks).

## URLs and click streams {#urls-and-click-streams}

This report shows the list of pages visited following a delivery. 

![](assets/s_ncs_user_url_report.png)

You can configure the contents of this report by selecting: the score chart to be displayed, the time filter (since the action launch, over the first 6 hours following launch, etc.) and the data display mode (by label, by URL, by category. Click **[!UICONTROL Refresh]** to confirm your selection.

The following rates are displayed in the upper section of the report:

* **[!UICONTROL Reactivity]** : Ratio of the number of targeted recipients having clicked in a delivery, in relation to the estimated number of targeted recipients having opened a delivery. Clicks on the opt-out link and on the mirror page are not taken into account.

  >[!NOTE]
  >
  >For more information on tracking opens, refer to [this section](metrics-calculation.md#tracking-opens-).

* **[!UICONTROL Distinct clicks]** : Number of distinct people having clicked at least once (excluding unsubscription link and mirror page) in a delivery. The rate displayed is calculated based on the number of messages delivered successfully. 
* **[!UICONTROL Cumulated clicks]** : Total number of clicks by targeted recipients (excluding unsubscription link and mirror page). The rate displayed is calculated based on the number of messages forwarded successfully.

**[!UICONTROL Platform average]** : This average rate, displayed under each rate (reactivity, distinct clicks, and cumulated clicks), is calculated for deliveries sent over the previous six months. Only deliveries with the same typology and on the same channel are taken into account. Proofs are excluded.

The central table provides the following information:

* **[!UICONTROL Clicks]** : Number of cumulated clicks, per link. 
* **[!UICONTROL Clicks (in %)]** : Breakdown of the number of clicks per link, in relation to the total number of cumulated clicks.

**[!UICONTROL Breakdown of clicks in time]**

This chart shows the breakdown of cumulated clicks per day.
-->

## Resumen de entregas {#delivery-summary}

Este informe proporciona toda la información principal sobre la entrega.

![](assets/user-report-summary.png)

**[!UICONTROL Target population]**

Esta sección tiene dos indicadores:

* **[!UICONTROL Initial population]** : Número total de destinatarios a quienes se realizó la entrega.
* **[!UICONTROL Messages rejected by the rule]** : número de direcciones ignoradas durante el análisis al aplicar las reglas de tipología: dirección no disponible, en cuarentena, en lista de bloqueados, etc. <!--For more information on typology rules, refer to this [page](../../delivery/using/steps-validating-the-delivery.md#validation-process-with-typologies).-->

**[!UICONTROL Causes of exclusion]**

El gráfico central muestra el desglose por regla de mensajes rechazados durante el análisis.

**[!UICONTROL Delivery statistics]**

Esta sección incluye los siguientes indicadores:

* **[!UICONTROL Messages to be delivered]** : Número total de mensajes que desea enviar después del análisis de envío.
* **[!UICONTROL Success]** : Número de mensajes procesados correctamente. La tasa asociada es la proporción respecto al número de mensajes que desea enviar.
* **[!UICONTROL Errors]** : Número total de errores acumulados durante los envíos y el procesamiento automático de los rechazos. La tasa asociada es la proporción respecto al número de mensajes que desea enviar.
* **[!UICONTROL New quarantines]** : Número de direcciones en cuarentena después de un envío fallido (usuario desconocido, dominio no válido). La tasa asociada es la proporción respecto al número de mensajes que desea enviar.

## Clics activos {#hot-clicks}

Este informe muestra el contenido del mensaje (HTML o texto) con el porcentaje de clics en los vínculos, por cada vínculo. Los bloques personalizados, los vínculos de cancelación de suscripción, los vínculos de páginas espejo y los vínculos de ofertas se tienen en cuenta en el total de clics acumulados, pero no se muestran en el informe.

>[!NOTE]
>
>Si la entrega contiene ofertas (interacción), aparece un cuadro en la parte superior del informe que muestra el porcentaje de clics en las ofertas.


## Estadísticas de seguimiento {#tracking-statistics}

Este informe ofrece estadísticas sobre las aperturas, los clics y las transacciones.

Permite realizar un seguimiento del impacto de marketing de la entrega. Se puede configurar el modo en que se muestran los valores cambiando la escala temporal (vista de 1 hora, de 3 horas, de 24 horas, etc.). Haga clic en **[!UICONTROL Refresh]** para confirmar la selección.

Este informe proporciona una tabla de valores y un gráfico de Pareto que muestra el tiempo necesario para que la entrega llegue a su máxima eficiencia. Se utilizan los siguientes indicadores:

* **[!UICONTROL Opens]** : Estimación del tiempo necesario para alcanzar un porcentaje del número total de mensajes abiertos. No se tienen en cuenta los correos electrónicos en formato de texto. [Más información](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clicks]** : Estimación del tiempo necesario para alcanzar un porcentaje del número total de clics registrados. No se tienen en cuenta los clics en el vínculo de exclusión ni de la página espejo.
<!--
* **[!UICONTROL Transactions]** : Time required to achieve a percentage of the total number of transactions following message reception. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->


## Informes acumulados {#cumulated-reports}

Se pueden mostrar informes acumulados sobre las entregas. Para ello, seleccione las entregas que desea comparar para obtener la lista de informes para estas entregas.

Para seleccionar entregas no adyacentes de la lista, mantenga pulsada la tecla CTRL mientras realiza la selección.

Para seleccionar entregas guardadas en una carpeta diferente, haga clic en el **[!UICONTROL Display sub-levels]** , accesible en la barra de herramientas. A continuación, se muestran en la misma lista.
