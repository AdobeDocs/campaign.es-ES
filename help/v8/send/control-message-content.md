---
product: campaign
title: Acerca de la capacidad de entrega en Adobe Campaign Classic
description: Obtenga más información acerca de la administración de la capacidad de entrega en Adobe Campaign
feature: Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: dcd3a9f9-5fe9-4c28-a4a5-5aed67b036ab
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 97%

---

# Control del contenido de los mensajes{#control-message-content}

Para asegurarse de que los mensajes de correo electrónico llegan a los destinatarios y mejoran la tasa de envío de correo electrónico, deben respetar una serie de reglas. De lo contrario, el contenido de ciertos mensajes puede detectarse como correo no deseado. Adobe Campaign proporciona varias herramientas para que el contenido cumpla con estas reglas.

Siga los principios que se enumeran a continuación al diseñar el contenido del mensaje:

* [Dirección del remitente](#sender-address): la dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado por él. El registro de dominios no debe privatizarse.
* [Personalización](#personalization): la personalización del contenido y la definición de una hora de envío por destinatario aumentan las posibilidades de que se abra el mensaje.
* Imágenes y texto: respete una proporción de texto/imagen adecuada (por ejemplo, 60 % de texto y 40 % de imágenes).
* [Vínculo de baja de suscripción](#opt-out) y página de destino: el vínculo de baja es esencial. Debe ser visible y válido, y el formulario debe ser funcional.
* Vista previa: utilice las herramientas que ofrece Adobe Campaign para comprobar y optimizar el contenido del correo electrónico ([Renderización de bandeja de entrada](#message-responsiveness), [SpamAssassin](#spamassassin)).

Para obtener sugerencias adicionales para optimizar la capacidad de entrega al diseñar contenido, consulte la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=es){target="_blank"}.

>[!NOTE]
>
>Para obtener más información sobre cómo editar el contenido del correo electrónico, consulte esta [página](defining-the-email-content.md).

## Dirección del remitente {#sender-address}

Algunos ISP verifican la validez de la dirección del remitente (**[!UICONTROL From]**) antes de aceptar mensajes. Una dirección mal formada puede hacer que el servidor receptor la rechace.

Debe asegurarse de proporcionar una dirección correcta en el nivel de instancia (menú **[!UICONTROL Tools > Advanced > deployment wizard...]**) o en los escenarios más utilizados.

Para obtener más información sobre la definición de la dirección del remitente, consulte esta [página](defining-the-email-content.md#sender).

## Personalización {#personalization}

Para mejorar la experiencia de los destinatarios y hacer que abran su correo electrónico, Adobe Campaign le permite personalizar sus mensajes.

Para obtener más información sobre el uso de los campos de personalización en Adobe Campaign, consulte [esta sección](personalization-fields.md).

## Formulario y vínculo de no participación {#opt-out}

De forma predeterminada, cuando se analiza el mensaje, una [regla de tipología](../../automation/campaign-opt/apply-rules.md) comprueba si se ha incluido un vínculo de no participación y genera una advertencia si falta. Puede cambiar esta regla para que se produzca un error en lugar de una simple advertencia y evitar que una entrega salga sin este vínculo.

Debe comprobar que el vínculo de exclusión funciona correctamente antes de cada envío. Por ejemplo, al enviar la prueba, asegúrese de que el vínculo sea válido, de que el formulario esté en línea y de que al validarlo se cambie el valor del campo **[!UICONTROL No longer contact this recipient]** a **[!UICONTROL Yes]**. Debe realizar esta comprobación sistemáticamente porque siempre puede haber errores humanos al introducir el vínculo o al cambiar el formulario.

Obtenga información sobre cómo insertar un vínculo de exclusión [en esta sección](personalization-blocks.md#ootb-personalization-blocks).

Si se detecta un problema relacionado con la baja después de que se inicie la entrega, aún es posible realizar una baja manualmente (mediante la función de actualización masiva, por ejemplo) para los destinatarios que hacen clic en el vínculo de exclusión incluso si no pudieron confirmar su elección.

Como regla general, no intente interferir con los destinatarios que deseen optar por la exclusión obligándolos a rellenar campos como, por ejemplo, su dirección de correo electrónico o su nombre. El formulario solo debe tener un botón de validación y la reconciliación solo debe realizarse en el identificador cifrado.

La solicitud de confirmación adicional no es fiable: un usuario puede tener dos direcciones de correo electrónico redirigidas al mismo cuadro (por ejemplo: firstname.lastname@club.com y firstname.lastname@internet-club.com). Si el destinatario solo puede recordar la primera dirección y desea cancelar la suscripción a través de un mensaje enviado a la otra, el formulario lo rechazará porque el identificador cifrado y la dirección de correo electrónico introducidos no coincidirán.

## Procesamiento de la bandeja de entrada {#message-responsiveness}

Antes de enviar el mensaje, puede probar la capacidad de respuesta comprobando el aspecto que tendrá el mensaje en diferentes dispositivos. Esto le permite asegurarse de que su mensaje se mostrará de una forma óptima en una gran variedad de clientes, correos web y dispositivos.

Para permitirlo, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite previsualizar el mensaje enviado en los diferentes contextos en los que se puede recibir.

Para obtener más información, consulte [Procesamiento de bandeja de entrada](inbox-rendering.md).

## SpamAssassin {#spamassassin}

Adobe Campaign se puede configurar para que funcione con SpamAssassin. Esto le permite puntuar correos electrónicos para determinar si un mensaje corre el riesgo de que las herramientas de filtrado de correo no deseado utilizadas durante la recepción lo consideren como no deseado.

Antes de iniciar una entrega, la pestaña **[!UICONTROL Preview]** le permite evaluar los riesgos. Un mensaje de advertencia le muestra el resultado de la prueba.

Obtenga más información en esta [sección](spamassassin.md).
