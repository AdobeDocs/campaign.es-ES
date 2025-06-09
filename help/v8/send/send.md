---
title: Envío y monitorización de correos electrónicos
description: Obtenga información acerca del ámbito y las características específicas del envío de correos electrónicos con Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 26%

---


# Envío y monitorización de correos electrónicos  {#send-and-monitor-emails}

Una vez configurada la entrega y lista para enviarla, asegúrese de ejecutar el análisis de entrega. [Más información](delivery-analysis.md)

Una vez finalizado, confirme la entrega para iniciar la entrega de mensajes.

Rastree la ejecución del envío desde la ficha **Envío**, a la que se puede acceder mediante el detalle del envío o a través de la lista de envíos.

## Monitorización de correos electrónicos {#email-monitoring}

Una vez enviado, compruebe su estado de envío en **Delivery Dashboard** y acceda a los registros de envío y a los informes para confirmar que los mensajes se han enviado correctamente.

Desde el panel de entregas, puede comprobar los mensajes procesados y los registros de auditoría de entregas. También puede controlar el estado de los mensajes en los registros de envío.

>[!NOTE]
>
>Los estados de envío no se muestran en tiempo real. Obtenga más información acerca del servicio de comentarios de correo electrónico [en esta sección](#email-feedback-service).


[Obtenga más información acerca de la monitorización de entregas en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=es){target="_blank"}

## MTA de Campaign {#mta}

El Agente de transferencia de correo (MTA) de Campaign v8 proporciona la mejor infraestructura de envío de su clase, lo que permite una capacidad de entrega, reputación, rendimiento, informes, gestión de devoluciones, ampliación de IP y administración de la configuración de conexión óptimas.

Disponible para todos los clientes de Campaign v8, garantiza la escalabilidad, un alto rendimiento de entrega y ayuda a enviar más correos electrónicos más rápido. Esto se logra con las nuevas técnicas de envío adaptable que modifican la configuración del envío de correo electrónico en tiempo real en función de los comentarios de los proveedores de servicio de Internet.

### Ventajas

Adobe Campaign usa un Agente de transferencia de correo (MTA) que ejecuta un MTA de correo electrónico comercial de SparkPost denominado **Momentum**.

Momentum representa una tecnología de MTA innovadora y de alto rendimiento que incluye gestión de devoluciones más inteligente y capacidad de optimización de envíos automatizados, lo que ayuda a los remitentes a lograr y mantener tasas de envío de bandeja de entrada óptimas.

* El MTA permite un aumento masivo en la velocidad de rendimiento general y una reducción significativa de las devoluciones suaves.
* Utiliza la tecnología de MTA más reciente para proporcionarle las velocidades de rendimiento óptimas para su envío de correo electrónico.
* Al adaptarse instantánea y automáticamente a los comentarios que recibe, también garantiza envíos de correos electrónicos más precisos e inteligentes con los datos de envío en tiempo real.

### Calificación de rechazo

Para los mensajes de error **sincrónico** de error de entrega, el MTA determina el tipo de devolución y calificación, y envía esa información a Campaign.

El MTA califica el rebote SMTP y devuelve esa calificación a Campaign en forma de código de rechazo asignado a un motivo y una calificación de Campaign.

>[!NOTE]
>
>Actualmente, las **devoluciones asincrónicas** están calificadas por el proceso de inMail a través de las reglas **[!UICONTROL Inbound email]**.

Obtenga más información sobre los errores de entrega en [esta sección](delivery-failures.md).


### Reglas MX específicas

Las reglas MX (Mail eXchanger) son las reglas que administran la comunicación entre un servidor emisor y un servidor receptor.

El MTA tiene sus propias reglas MX que le permiten personalizar el rendimiento por dominio en función de su propia reputación histórica de correo electrónico y de los comentarios en tiempo real procedentes de los dominios a los que envía correos electrónicos.

### Firma DKIM

Domain Keys Identified Mail (DKIM) es un método de autenticación que se utiliza para detectar direcciones de remitente falsificadas (comúnmente denominadas suplantación de identidad).

En Adobe Campaign, la firma de autenticación de correo electrónico de DKIM la realiza el MTA.

Obtenga más información sobre DKIM en la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#authentication){target="_blank"}.

## Servicio de comentarios de correo electrónico {#email-feedback-service}

El servicio de comentarios de correo electrónico de Campaign (EFS) informa del estado de cada envío de correo electrónico realizado con Adobe Campaign.

Una vez iniciada la entrega, no hay ningún cambio en el porcentaje **[!UICONTROL Success]** cuando el mensaje se transmite correctamente de Campaign al servidor de correo. Los registros de envío muestran el estado **[!UICONTROL Taken into account by the service provider]** de cada dirección de destino.

Cuando el mensaje se envía realmente a los perfiles de destino y una vez que se transmite esta información en tiempo real desde el servidor de correo, los registros de envío muestran el estado **[!UICONTROL Sent]** para cada dirección que recibió el mensaje correctamente. El porcentaje de **[!UICONTROL Success]** se incrementa en consecuencia con cada envío correcto.

Cuando se generan informes de los mensajes de rebote duro desde el servidor de correo, su estado de registro cambia de **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Cuando se generan informes de los mensajes de rebote suave desde el servidor de correo, su estado de registro permanece sin cambios (**[!UICONTROL Taken into account by the service provider]**): solo se actualiza [el motivo del error](delivery-failures.md#delivery-failure-reasons)<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. El porcentaje de **[!UICONTROL Success]** permanece sin cambios. A continuación, se vuelven a intentar los mensajes de devolución suave a lo largo del [período de validez del envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=es#defining-validity-period){target="_blank"}:

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Success]** sube en consecuencia.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]**. El porcentaje de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece sin cambios.

>[!NOTE]
>
>Para obtener más información acerca de las devoluciones suaves y duras, consulte [esta sección](delivery-failures.md#delivery-failure-reasons).
>
>Para obtener más información sobre reintentos después de un error temporal de envío, consulte [esta sección](delivery-failures.md#retries).

La tabla siguiente muestra cómo se actualizan los KPI y los estados de registros de envío en cada paso del proceso de envío.

| Paso en el proceso de envío | Resumen de KPI | Estado de envío de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente desde Campaign al servidor de correo | **[!UICONTROL Success]** no se muestra el porcentaje (comienza en 0 %) | El proveedor de servicios lo tiene en cuenta |
| Los mensajes de devolución dura se informan desde el servidor de correo | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |
| Los mensajes de devolución suave se informan desde el servidor de correo | No hay cambios en el porcentaje de **[!UICONTROL Success]** | El proveedor de servicios lo tiene en cuenta |
| Los reintentos de mensajes de devolución suave se realizan correctamente | El porcentaje de **[!UICONTROL Success]** sube en consecuencia | Enviado |
| Error en los reintentos de mensajes de devolución suave | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |
