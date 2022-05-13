---
title: Send with the Enhanced MTA in Adobe Campaign
description: Obtenga información acerca del ámbito y las características específicas del envío de correos electrónicos con el MTA mejorado de Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
source-git-commit: 448436d56d14dca2d18088ebfc94f9e21ebb58c4
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 69%

---

# Envío con el servidor de correo mejorado {#sending-with-enhanced-mta}

****

Se implementa para mejorar la escalabilidad, aumentar el rendimiento del envío y permitir enviar más correos electrónicos más rápido. Esto se logra con las nuevas técnicas de envío adaptable que modifican la configuración del envío de correo electrónico en tiempo real en función de los comentarios de los proveedores de servicio de Internet.

## Uso y beneficios

**¿Qué es el servidor de correo mejorado (MTA)?**

****

Momentum representa una tecnología de MTA innovadora y de alto rendimiento que incluye gestión de devoluciones más inteligente y capacidad de optimización de envíos automatizados, lo que ayuda a los remitentes a lograr y mantener tasas de envío de bandeja de entrada óptimas.

**¿Cuáles son los beneficios?**

* The Enhanced MTA allows a massive increase in overall throughput speed and a significant reduction in soft bounces.
* It uses the latest MTA technology to provide you with the optimal throughput speeds for your email delivery.
* Al adaptarse instantánea y automáticamente a los comentarios que recibe, también garantiza envíos de correos electrónicos más precisos e inteligentes con los datos de envío en tiempo real.

## Especificaciones del MTA mejorado {#enhanced-mta-impacts}

### Calificación de rechazo

****

El servidor de correo mejorado califica el rebote SMTP y devuelve esa calificación a Campaign en forma de código de rechazo asignado a un motivo y una calificación de Campaign.

>[!NOTE]
>
>******[!UICONTROL Inbound email]** [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification)<!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

[](delivery-failures.md)

### Período de validez

El servidor de correo mejorado solo utilizará la configuración del período de validez de los envíos de Campaign si se establece en **3,5 días o menos**. Si define un valor superior a 3,5 días en Campaign, no se tendrá en cuenta.

Por ejemplo, si el período de validez se establece en el valor predeterminado de 5 días en Campaign, los mensajes de rebote suave se incluirán en la cola de reintentos del servidor de correo mejorado y se volverá a intentar su envío durante un máximo de 3,5 días a partir de la fecha en que el mensaje llegue al servidor de correo mejorado. En ese caso, no se utilizará el valor establecido en Campaign.

Una vez que un mensaje ha estado en la cola del servidor de correo mejorado durante 3,5 días y no se ha podido entregar, se agotará el tiempo de espera y su estado se actualizará de **[!UICONTROL Sent]** a **[!UICONTROL Failed]** en los registros de envío.

[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period)

### Reintentos

Los reintentos de rebote suave y el periodo entre ellos los determina el servidor de correo mejorado en función del tipo y la gravedad de las respuestas de devoluciones procedentes del dominio de correo electrónico del mensaje.

>[!NOTE]
>
>The retry settings in the delivery properties are not used by Campaign.

[](delivery-failures.md#retries)

### Specific MX rules

Las reglas MX (Mail eXchanger) son las reglas que administran la comunicación entre un servidor emisor y un servidor receptor.

El servidor de correo mejorado utiliza sus propias reglas MX que le permiten personalizar el rendimiento por dominio en función de su propia reputación histórica de correo electrónico y de los comentarios en tiempo real procedentes de los dominios a los que envía correos electrónicos.

### Firma DKIM

Domain Keys Identified Mail (DKIM) is an authentication method that is used to detect forged sender addresses (commonly called spoofing).

In Adobe Campaign, DKIM email authentication signing is performed by the Enhanced MTA.

[](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#authentication)

## Servicio de comentarios de correo electrónico {#email-feedback-service}

Con el servicio de comentarios de correo electrónico (SCCE), se informa del estado de cada correo electrónico con precisión, ya que los comentarios se capturan directamente desde el servidor de correo mejorado.

Una vez que se ha iniciado el envío, no se produce ningún cambio en el porcentaje de **[!UICONTROL Success]** cuando el mensaje se transmite correctamente de Campaign al servidor de correo mejorado.

Los registros de envío muestran el estado **[!UICONTROL Taken into account by the service provider]** de cada dirección de destino.

Cuando el mensaje se envía realmente a los perfiles objetivo y una vez que se transmite esta información en tiempo real desde el servidor de correo mejorado, los registros de envío muestran el estado **[!UICONTROL Sent]** para cada dirección que recibió el mensaje correctamente. El porcentaje de **[!UICONTROL Success]** se incrementa en consecuencia con cada envío correcto.

Cuando el servidor de correo mejorado devuelve mensajes de rebote duro, su estado de registro cambia de **[!UICONTROL Taken into account by the service provider]** a **[!UICONTROL Failed]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Cuando los mensajes de rebote suaves vuelven a informarse desde el servidor de correo mejorado, su estado de registro permanece sin cambios (**[!UICONTROL Taken into account by the service provider]**): solo se actualiza[la razón de error](delivery-failures.md#delivery-failure-reasons)<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. El porcentaje de **[!UICONTROL Success]** permanece sin cambios. [](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period)

* Si un reintento se realiza correctamente antes del final del período de validez, el estado del mensaje cambia a **[!UICONTROL Sent]** y el porcentaje de **[!UICONTROL Success]** sube en consecuencia.

* De lo contrario, el estado cambia a **[!UICONTROL Failed]**. El porcentaje de **[!UICONTROL Success]** <!--and **[!UICONTROL Bounces + errors]** -->permanece sin cambios.

>[!NOTE]
>
>Para obtener más información acerca de las devoluciones suaves y duras, consulte [esta sección](delivery-failures.md#delivery-failure-reasons).
>
>Para obtener más información sobre reintentos después de un error temporal de envío, consulte [esta sección](delivery-failures.md#retries).

The table below shows how the KPIs and sending logs statuses are updated at each step of the sending process with the EFS capability.

| Paso en el proceso de envío | Resumen de KPI | Estado de envío de registros |
|--- |--- |--- |
| El mensaje se retransmite correctamente desde Campaign al servidor de correo mejorado | **[!UICONTROL Success]** no se muestra el porcentaje (comienza en 0 %) | El proveedor de servicios lo tiene en cuenta |
| Los mensajes de devolución dura se informan desde el servidor de correo mejorado | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |
| Los mensajes de devolución suave se informan desde el servidor de correo mejorado | No hay cambios en el porcentaje de **[!UICONTROL Success]** | El proveedor de servicios lo tiene en cuenta |
| Los reintentos de mensajes de devolución suave se realizan correctamente | El porcentaje de **[!UICONTROL Success]** sube en consecuencia | Enviado |
| Error en los reintentos de mensajes de devolución suave | No hay cambios en el porcentaje de **[!UICONTROL Success]** | Error |

