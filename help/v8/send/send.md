---
title: Envío y monitorización de los correos electrónicos
description: Obtenga información sobre el ámbito y las características específicas del envío de correos electrónicos con Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 31%

---


# Envío y monitorización de los correos electrónicos

Una vez configurada la entrega y lista para enviarla, asegúrese de haber ejecutado el análisis de entrega.

![](../assets/do-not-localize/book.png) [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery){target=&quot;_blank&quot;}

Una vez finalizado, confirme la entrega para iniciar la entrega de mensajes.

También puede realizar lo siguiente:

* programar el envío a más adelante mediante [la opción pospone the delivery](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;},
* enviar a varios lotes utilizando [múltiples olas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}.

Rastree la ejecución del envío desde el **Entrega** , a la que se puede acceder mediante el detalle de este envío o a través de la lista de envíos.

## Supervisión de los correos electrónicos

Una vez enviado, compruebe su estado de entrega en el panel de entregas y acceda a los registros de envío y a los informes para confirmar que los mensajes se han enviado correctamente.

![](../assets/do-not-localize/book.png) [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target=&quot;_blank&quot;}


## MTA de campaña {#mta}

El Agente de transferencia de correo (MTA) de Campaign v8 proporciona una infraestructura de envío de primer nivel que permite una capacidad de envío óptima, reputación, rendimiento, sistema de informes, gestión de devoluciones, ampliación de IP y administración de la configuración de conexión.

Disponible para todos los clientes de Campaign v8, garantiza la escalabilidad, un alto rendimiento de entrega y ayuda a enviar más correos electrónicos más rápido. Esto se logra con las nuevas técnicas de envío adaptable que modifican la configuración del envío de correo electrónico en tiempo real en función de los comentarios de los proveedores de servicio de Internet.

### Ventajas

Adobe Campaign utiliza un agente de transferencia de correo (MTA) que ejecuta el MTA de correo electrónico comercial de SparkPost llamado **Momentum**.

Momentum representa una tecnología de MTA innovadora y de alto rendimiento que incluye gestión de devoluciones más inteligente y capacidad de optimización de envíos automatizados, lo que ayuda a los remitentes a lograr y mantener tasas de envío de bandeja de entrada óptimas.

* El MTA permite un aumento masivo de la velocidad de rendimiento general y una reducción significativa de los rechazos leves.
* Utiliza la última tecnología MTA para proporcionarle las velocidades de rendimiento óptimas para su envío de correo electrónico.
* Al adaptarse instantánea y automáticamente a los comentarios que recibe, también garantiza envíos de correos electrónicos más precisos e inteligentes con los datos de envío en tiempo real.

### Calificación de rechazo

Para **sincrónica** mensajes de error de error de entrega, el MTA determina el tipo de rechazo y la calificación, y envía esa información a Campaign.

El MTA clasifica el rechazo SMTP y envía esa calificación a Campaign en forma de código de rechazo asignado a un motivo y calificación de devolución de Campaign.

>[!NOTE]
>
>Actualmente **asincrónico** las devoluciones se clasifican mediante el proceso inMail a través del **[!UICONTROL Inbound email]** reglas. Para obtener más información, consulte [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

Obtenga más información sobre los errores de entrega en [esta sección](delivery-failures.md).


### Reglas MX específicas

Las reglas MX (Mail eXchanger) son las reglas que administran la comunicación entre un servidor emisor y un servidor receptor.

El MTA tiene sus propias reglas MX que le permiten personalizar el rendimiento por dominio en función de su propia reputación histórica de correo electrónico y de los comentarios en tiempo real procedentes de los dominios a los que envía correos electrónicos.

### Firma DKIM

Correo identificado de claves de dominio (DKIM) es un método de autenticación que se utiliza para detectar direcciones de remitente falsificadas (comúnmente denominadas suplantación de identidad).

En Adobe Campaign, la firma de autenticación de correo electrónico DKIM la realiza el MTA.

Obtenga más información sobre DKIM en la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#authentication){target=&quot;_blank&quot;}.

## Servicio de comentarios de correo electrónico {#email-feedback-service}

Con la capacidad Servicio de comentarios de correo electrónico (EFS) , el estado de cada correo electrónico se informa con precisión, ya que los comentarios se capturan directamente desde el MTA.

Una vez iniciado el envío, no hay ningún cambio en la variable **[!UICONTROL Success]** porcentaje cuando el mensaje se transmite correctamente de Campaign al MTA.

Los registros de envío muestran el estado **[!UICONTROL Taken into account by the service provider]** de cada dirección de destino.

Cuando el mensaje se envía realmente a los perfiles de destino y una vez que esta información se devuelve en tiempo real desde el MTA, los registros de envío muestran la variable **[!UICONTROL Sent]** para cada dirección que recibió el mensaje correctamente. El porcentaje de **[!UICONTROL Success]** se incrementa en consecuencia con cada envío correcto.

Cuando los mensajes rechazados en el disco duro se devuelven desde el MTA, su estado de registro cambia de **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Cuando los mensajes de devolución en blanco se devuelven desde el MTA, su estado de registro permanece sin cambios (**[!UICONTROL Taken into account by the service provider]**): solo la variable [motivo del error](delivery-failures.md#delivery-failure-reasons) se actualiza<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. El porcentaje de **[!UICONTROL Success]** permanece sin cambios. A continuación, se vuelven a intentar los mensajes de devolución en blanco durante toda la entrega [periodo de validez](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}:

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Success]** sube en consecuencia.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]**. El porcentaje de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece sin cambios.

>[!NOTE]
>
>Para obtener más información acerca de las devoluciones suaves y duras, consulte [esta sección](delivery-failures.md#delivery-failure-reasons).
>
>Para obtener más información sobre reintentos después de un error temporal de envío, consulte [esta sección](delivery-failures.md#retries).

La tabla siguiente muestra cómo se actualizan los KPI y los estados de registros de envío en cada paso del proceso de envío con la capacidad EFS.

| Paso en el proceso de envío | Resumen de KPI | Estado de envío de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente de Campaign al MTA | **[!UICONTROL Success]** no se muestra el porcentaje (comienza en 0 %) | El proveedor de servicios lo tiene en cuenta |
| Los mensajes rechazados se informan desde el MTA | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |
| Los mensajes de devolución en blanco se informan desde el MTA | No hay cambios en el porcentaje de **[!UICONTROL Success]** | El proveedor de servicios lo tiene en cuenta |
| Los reintentos de mensajes de devolución suave se realizan correctamente | El porcentaje de **[!UICONTROL Success]** sube en consecuencia | Enviado |
| Error en los reintentos de mensajes de devolución suave | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |
