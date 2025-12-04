---
title: Monitorización de entregas en la IU de Campaign
description: Obtenga información sobre cómo acceder a la lista de entregas y utilizar el panel de entregas para monitorizar las entregas
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 70%

---

# Monitorización de entregas en la IU de Campaign {#delivery-dashboard}

La monitorización de las entregas es esencial para garantizar que las campañas sean eficientes y lleguen a los clientes. Adobe Campaign le proporciona herramientas para acceder a sus envíos y monitorizar su rendimiento a través de la lista de envíos y el panel de entregas.

## Acceso a la lista de envíos {#list-of-deliveries}

Puede acceder a las entregas desde la lista de entregas a través del nodo **[!UICONTROL Campaign Management > Deliveries]** del árbol.

![](assets/deliveries-list.png)

De forma predeterminada, la lista de entregas contiene los nombres y estados de las entregas creados en el nodo seleccionado. También muestra el número de mensajes que se van a enviar, procesados y enviados con éxito.

* El número de **[!UICONTROL Messages to send]** corresponde al número de destinatarios objetivo tras realizar el análisis y antes de la entrega.
* El número de mensajes de la columna **[!UICONTROL Success]** corresponde al número de mensajes que envía el servidor y que reciben los destinatarios.
* El número de mensajes **[!UICONTROL Processed]** corresponde al número de mensajes recibidos más el número de mensajes con errores.

>[!NOTE]
>
>Para las entregas grandes, quizá desee actualizar estos valores. Para ello, seleccione la entrega en cuestión y, a continuación, haga clic con el botón derecho del ratón. Seleccione **[!UICONTROL Action > Recompute delivery and tracking indicators...]** y, a continuación, utilice el asistente para actualizar esta información.

## Resumen del panel de entregas {#delivery-dashboard-overview}

El **panel de control de entregas** es fundamental para controlar las entregas y los problemas que puedan ser detectados durante la entrega de mensajes.

Permite recuperar información de una entrega y editarla si es necesario. Tenga en cuenta que el contenido de las pestañas no se puede cambiar una vez realizada la entrega.

A continuación, se muestra la información que puede monitorizar en las distintas pestañas disponibles en el panel de control:

* [Resumen de entregas](#delivery-summary)
* [Informes de envío](#delivery-reports)
* [Registros de envío, páginas espejo, exclusiones](#delivery-logs-and-history)
* [Registros de seguimiento de entregas e historial](#tracking-logs)
* [Procesamiento de entregas](#delivery-rendering)
* [Auditoría de entregas](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Temas relacionados:**

* [Comprender los errores de envío](delivery-failures.md)
* [Administración de cuarentena](quarantines.md)
* [Prácticas recomendadas de entregas](../start/delivery-best-practices.md)
* [Administración de entregabilidad](about-deliverability.md)

## Resumen de entregas {#delivery-summary}

La pestaña **[!UICONTROL Summary]** contiene las características de la entrega: estado de la entrega, canal utilizado, información sobre el remitente, asunto, información sobre la ejecución.

## Informes de envío {#delivery-reports}

El vínculo **[!UICONTROL Reports]** le permite ver un conjunto de informes relativos a la acción de entrega: informes de entregas generales, informes detallados, informes de entregas, distribución de mensajes fallidos, tasa de apertura, clics y transacciones, etc.**[!UICONTROL Summary]**

El contenido de esta pestaña se puede configurar según sus necesidades. Para obtener más información sobre los informes de entregas, consulte [esta sección](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Registros de envíos, historial y exclusiones {#delivery-logs-and-history}

La pestaña **[!UICONTROL Delivery]** ofrece un historial de los sucesos en esta entrega. Contiene los registros de entregas, es decir, la lista de mensajes enviados y su estado y los mensajes asociados.

Para una entrega, puede mostrar, por ejemplo, solo los destinatarios con una entrega fallido o una dirección en cuarentena. Para ello, haga clic en el botón **[!UICONTROL Filters]** y seleccione **[!UICONTROL By state]**. Seleccione el estado en la lista desplegable. Hay varios estados enumerados en la página [estados de entrega](delivery-statuses.md).

>[!NOTE]
>
>La lista que muestra los registros de envío se puede personalizar, como cualquier lista de Campaign. Por ejemplo, puede agregar una columna para saber qué dirección IP envió cada correo electrónico en una entrega. Para obtener más información sobre la configuración de listas, consulte [esta sección](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

El enlace **[!UICONTROL Display the mirror page for this message...]** permite ver la página espejo del contenido de la entrega seleccionado en la lista en una nueva ventana.

La página espejo solo está disponible para los envíos para los que se ha definido contenido HTML. Para obtener más información, consulte [Vínculo a la página espejo](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Registros de seguimiento de entregas e historial {#tracking-logs}

La pestaña **[!UICONTROL Tracking]** enumera el historial de seguimiento de esta entrega. Esta pestaña muestra los datos de seguimiento de los mensajes enviados, es decir, todas las direcciones URL sobre las que Adobe Campaign realiza un seguimiento. Los datos de seguimiento se actualizan cada hora.

>[!NOTE]
>
>Si el seguimiento no está habilitado para una entrega, esta pestaña no se muestra.

La configuración de seguimiento se realiza en la fase adecuada del asistente de envíos. Consulte [Configuración de los vínculos rastreados](tracking.md).

Los datos de **[!UICONTROL Tracking]** se interpretan en los informes de entrega. Consulte [esta sección](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Procesamiento de la bandeja de entrada {#delivery-rendering}

La pestaña **[!UICONTROL Inbox rendering]** le permite obtener una previsualización del mensaje en los diferentes contextos en los que se puede recibir y comprobar la compatibilidad en las aplicaciones y los escritorios principales.

Así, puede asegurarse de que su mensaje se mostrará a los destinatarios de una forma óptima en una gran variedad de clientes, correos web y dispositivos.

Para obtener más información sobre la renderización de la bandeja de entrada, consulte [esta página](inbox-rendering.md).


## Auditoría de entregas {#delivery-audit-}

La pestaña **[!UICONTROL Audit]** contiene el registro de entregas y todos los mensajes correspondientes a las pruebas.

El botón **[!UICONTROL Refresh]** permite actualizar los datos. Utilice el botón **[!UICONTROL Filters]** para definir un filtro en los datos.

Los iconos especiales permiten identificar errores o advertencias. Consulte [Análisis de envío](delivery-analysis.md).

La subpestaña **[!UICONTROL Proofs]** permite ver la lista de pruebas que se han enviado.

![](assets/s_ncs_user_delivery_log_tab.png)

Puede modificar la información mostrada en esta ventana (y la de las pestañas **[!UICONTROL Delivery]** y **[!UICONTROL Tracking]**) seleccionando las columnas que desea mostrar. Para ello, haga clic en el icono **[!UICONTROL Configure list]** situado en la esquina inferior derecha. Para obtener más información sobre la configuración de listas, consulte [esta sección](../config/ui-settings.md#customize-lists).

## Sincronización del panel de control de entregas {#delivery-dashboard-synchronization}

En el panel de control de entregas, se recomienda comprobar los mensajes procesados y los registros de entregas para asegurarse de que su entrega se haya realizado correctamente.

Algunos indicadores o estados pueden ser incorrectos o no estar actualizados; esto puede resolverse con las soluciones siguientes:

* Si su estado de entrega es incorrecto, compruebe que se hayan realizado todas las aprobaciones necesarias para esta entrega o que los flujos de trabajo técnicos de **[!UICONTROL operationMgt]** y **[!UICONTROL deliveryMgt]** se estén ejecutando sin errores.

* Si el contador de entregas no coincide con su entrega, intente volver a calcular los indicadores haciendo clic con el botón derecho en la entrega correspondiente de Adobe Campaign Explorer y seleccionando **[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]** para volver a sincronizar. Para obtener más información sobre los indicadores de seguimiento, consulte [esta sección](../reporting/delivery-reports.md#tracking-indicators).

También puede rastrear las entregas con diferentes informes a través del panel de control de entrega. Para obtener más información, consulte [esta sección](../reporting/delivery-reports.md).

>[!NOTE]
>
>Como usuario de Cloud Services administrados de Campaign v8, Adobe supervisa y administra la infraestructura. Si experimenta problemas persistentes con los indicadores de entrega o la sincronización del panel, póngase en contacto con el Servicio de atención al cliente de Adobe.

## Solución de problemas de entregas lentas {#troubleshooting-slow-deliveries}

Si su envío parece tardar más de lo normal después de hacer clic en el botón **[!UICONTROL Send]**, compruebe las siguientes causas potenciales:

### Problemas de reputación de direcciones IP

Es posible que algunos proveedores de correo electrónico hayan agregado sus direcciones IP a una lista de bloqueados. Compruebe sus registros de envío (broadlogs) en la pestaña **[!UICONTROL Delivery]** para ver mensajes de rechazo que indiquen problemas de reputación. Consulte la sección [supervisión de la capacidad de envío](monitoring-deliverability.md) para obtener instrucciones sobre la administración de la reputación.

### Tamaño y complejidad de la entrega

Su entrega puede ser demasiado grande para procesarlo rápidamente. Esto puede ocurrir con:

Personalización de JavaScript de gran tamaño que requiere un procesamiento de datos significativo para cada destinatario.

Envío con un peso de más de 60 kilobytes debido al gran contenido de HTML, las imágenes incrustadas o la personalización extensa.

Consulte [Prácticas recomendadas de envío](../start/delivery-best-practices.md) para obtener más información sobre las directrices de contenido y las prácticas recomendadas de personalización. El tamaño máximo recomendado es de unos 35 KB para obtener un rendimiento óptimo.

### Rendimiento del sistema

Los problemas del sistema pueden impedir que los servidores procesen los envíos de forma eficaz. Si cree que hay problemas de rendimiento, compruebe los registros de envío para ver si hay errores de tiempo de espera o problemas de comunicación.

>[!NOTE]
>
>Como usuario de Cloud Services administrados de Campaign v8, la supervisión de la infraestructura del servidor la administra Adobe. Si experimenta problemas de rendimiento persistentes con las entregas, póngase en contacto con el Servicio de atención al cliente de Adobe con sus registros de entregas.

