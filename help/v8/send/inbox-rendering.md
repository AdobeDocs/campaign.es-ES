---
product: campaign
title: Procesamiento de la bandeja de entrada en Campaign
description: Obtenga información sobre cómo capturar las renderizaciones de correo electrónico y ponerlas a disposición en un informe dedicado
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 100%

---

# Procesamiento de la bandeja de entrada{#inbox-rendering}

## Acerca del procesamiento de la bandeja de entrada {#about-inbox-rendering}

Antes de pulsar el botón **Send**, asegúrese de que su mensaje se mostrará a los destinatarios de una forma óptima en una gran variedad de clientes, correos Web y dispositivos web.

Para permitir esto, Adobe Campaign aprovecha la solución de prueba de correo electrónico basada en Web [Litmus](https://litmus.com/email-testing){target="_blank"} para detectar las irregularidades y señalarlas en un informe dedicado. Esto le permite obtener una previsualización del mensaje enviado en los diferentes contextos en los que se puede recibir y comprobar la compatibilidad en las aplicaciones y los escritorios principales.

>[!CAUTION]
>La renderización de la bandeja de entrada no es compatible con [envíos recurrentes](../../automation/workflow/recurring-delivery.md).

Litmus es una aplicación de validación y previsualización de correo electrónico con numerosas funciones. Permite a los creadores de contenido de correo electrónico obtener una previsualización del contenido de sus mensajes en más de 70 procesadores de correo electrónico, como la bandeja de entrada de Gmail o el cliente de correo de Apple.

Los clientes móviles, de mensajería y de correo web disponibles para **Renderización de la bandeja de entrada** en Adobe Campaign se enumeran en el [sitio web de Litmus](https://litmus.com/email-testing){target="_blank"} (haga clic en **Ver todos los clientes de correo electrónico**).

>[!NOTE]
>
>No es necesario renderizar la bandeja de entrada para probar la personalización en los envíos. La personalización puede comprobarse con las herramientas de Adobe Campaign como **[!UICONTROL Preview]** y [Pruebas](preview-and-proof.md#send-proofs).

## Acerca de los tokens de Litmus {#about-litmus-tokens}

Ya que Litmus es un servicio de terceros, funciona con un modelo de crédito. Cada vez que un usuario usa las funciones de Litmus, se reduce su crédito.

En Adobe Campaign, el crédito corresponde al número de representaciones disponibles (conocidas como tokens).

>[!NOTE]
>
>El número de tokens de Litmus disponibles depende de la licencia adquirida en Campaign. Compruebe el acuerdo de licencia.

Cada vez que se utiliza la función **[!UICONTROL Inbox rendering]** en un envío, cada renderización generada reduce en uno los tokens disponibles.

>[!IMPORTANT]
>
>Los tokens corresponden a cada renderización individual y no al informe completo de renderización de la Bandeja de entrada, lo que significa que:
>
>* Cada vez que se genera el informe de renderización de la Bandeja de entrada, se resta un token por cada cliente de mensajería: uno para la renderización de Outlook 2000, uno para la renderización de Outlook 2010, uno para la renderización de Apple Mail 9, etc.
>* Para el mismo envío, si vuelve a generar la renderización de la bandeja de entrada, el número de tokens disponibles se reduce de nuevo según la cantidad de renderizaciones generadas.
>

El número de tokens restantes disponibles se muestra en el [Informe de renderizado de la bandeja de entrada](#inbox-rendering-report).

![](assets/s_tn_inbox_rendering_tokens.png)

Normalmente, la función de renderización de la bandeja de entrada se utiliza para probar el marco HTML de un correo electrónico recién diseñado. Cada renderización requiere aproximadamente 70 tokens (dependiendo de la cantidad de entornos en los que se pruebe). Sin embargo, en algunos casos puede necesitar varios informes de renderización de la bandeja de entrada para probar al completo su envío. Por lo tanto, puede requerir más tokens para realizar varias comprobaciones.

## Acceso al informe de procesamiento de la bandeja de entrada {#accessing-the-inbox-rendering-report}

Una vez que haya creado su envío de correo electrónico y definido su contenido, así como la población de destino, siga los pasos a continuación.

Para obtener más información sobre la creación, el diseño y la segmentación un envío, consulte [esta sección](defining-the-email-content.md).

1. En la barra superior del envío, haga clic en el botón **[!UICONTROL Inbox rendering]**.

1. Seleccione **[!UICONTROL Analyze]** para iniciar el proceso de captura.

   ![](assets/s_tn_inbox_rendering_button.png)

   Se envía una prueba. Se puede acceder a las miniaturas de renderización de esa prueba unos minutos después de enviar los mensajes de correo electrónico. Para obtener más información la entrega de pruebas, consulte [esta sección](preview-and-proof.md#send-proofs).

1. Una vez enviada, la prueba aparece en la lista de envío. Haga doble clic en ella.

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. Vaya a la pestaña **Inbox Rendering** de la prueba.

   ![](assets/s_tn_inbox_rendering_tab.png)

   Se muestra el informe de renderización de la bandeja de entrada.

## Informe de procesamiento de la bandeja de entrada {#inbox-rendering-report}

Este informe muestra las renderizaciones de la bandeja de entrada tal y como aparecen al destinatario. Las renderizaciones pueden variar en función del modo en que el destinatario abra el envío de correo electrónico: en un navegador, en un dispositivo móvil o a través de una aplicación de correo electrónico.

La sección superior presenta la repartición del número de mensajes recibidos, no deseados (spam), no recibidos o pendientes de recepción a través de una representación gráfica codificada mediante colores.

![](assets/s_tn_inbox_rendering_summary.png){width="40%" align="left"}

Pase el puntero por encima del gráfico para ver los detalles de cada color. Haga clic en un elemento de la lista para ocultar o mostrar la categoría correspondiente en el gráfico.

El cuerpo del informe se divide en tres partes: **[!UICONTROL Mobile]**, **[!UICONTROL Desktop]** y **[!UICONTROL Webmails]**. Desplácese hacia abajo por el informe para mostrar todas las representaciones agrupadas en estas tres categorías.

![](assets/s_tn_inbox_rendering_report.png)

Para obtener los detalles de cada informe, haga clic en la tarjeta correspondiente. Se muestra la renderización del método de recepción seleccionado.

![](assets/s_tn_inbox_rendering_example.png)
