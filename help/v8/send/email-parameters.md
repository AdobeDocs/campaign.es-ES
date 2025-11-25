---
title: Parámetros de correo electrónico en Adobe Campaign
description: Obtenga información sobre las opciones y la configuración específicas del envío de correo electrónico en Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 6b70ad987b828dc1c17bc4f0683046be4eff0408
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 44%

---

# Parámetros del correo electrónico {#email-parameters}

Esta sección presenta las opciones y los parámetros disponibles en las propiedades de envío específicas de la entrega por correo electrónico.

## Usar CCO del correo electrónico {#email-bcc}

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma. Esta opción se detalla en [esta página](email-bcc.md).

## Seleccionar formatos de mensaje {#selecting-message-formats}

Puede cambiar el formato de los mensajes de correo electrónico enviados. Para ello, edite las propiedades de la entrega y haga clic en la pestaña **[!UICONTROL Delivery]**.

![](assets/email-message-format.png)

Seleccione el formato del correo electrónico en la sección inferior de la ventana:

* **[!UICONTROL Use recipient preferences]** (modo predeterminado)

  El formato de mensaje se define según los datos almacenados en el perfil de destinatario y se almacena de forma predeterminada en el campo **[!UICONTROL email format]** (@emailFormat). Si un destinatario desea recibir mensajes en un formato determinado, este es el formato enviado. Si el campo no está rellenado, se envía un mensaje multipart-alternative (consulte a continuación).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  El mensaje contiene ambos formatos: texto y HTML. El formato que se muestra al recibirlo depende de la configuración del software de correo del destinatario (multipart-alternative).

  >[!IMPORTANT]
  >
  >Esta opción incluye ambas versiones del documento. Por lo tanto, reduce el rendimiento de entrega, ya que el tamaño del mensaje es mayor.

* **[!UICONTROL Send all messages in text format]**

  El mensaje se envía en formato de texto. El formato HTML no se envía, pero se utiliza solo para la página espejo cuando el destinatario hace clic en el mensaje.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Establecer codificación de caracteres {#character-encoding}

En la pestaña **[!UICONTROL SMTP]** de los parámetros de entrega, la sección **[!UICONTROL Character encoding]** le permite establecer una codificación específica.

La codificación predeterminada es UTF-8. Si algunos de los proveedores de correo electrónico de los destinatarios no admiten la codificación estándar UTF-8, es posible que desee configurar una codificación específica para que muestre correctamente los caracteres especiales a los destinatarios de los mensajes de correo electrónico.

Por ejemplo, desea enviar un correo electrónico que contenga caracteres japoneses. Para asegurarse de que todos los caracteres se mostrarán correctamente a los destinatarios en Japón, es posible que desee utilizar una codificación que admita los caracteres japoneses en lugar de la codificación UTF-8 estándar.

Para ello, seleccione la opción **[!UICONTROL Force the encoding used for messages]** en la sección **[!UICONTROL Character encoding]** y elija una codificación en la lista desplegable que se muestra.

![](assets/email-smtp-encoding.png)

## Administrar correos electrónicos rechazados {#managing-bounce-emails}

La pestaña **[!UICONTROL SMTP]** de las propiedades de entrega también permite configurar la administración de los correos electrónicos rechazados.

* **[!UICONTROL Errors-to-address]**: de forma predeterminada, los correos electrónicos rechazados se reciben en el cuadro de error predeterminado de la plataforma, pero se puede definir una dirección de error específica para una entrega.

* **[!UICONTROL Bounce address]**: también puede definir otra dirección a la que se reenviarán los correos electrónicos rechazados sin procesar. Esta dirección permite investigar las razones de la devolución cuando la aplicación no pudo calificar automáticamente los correos electrónicos.

Cada uno de estos campos se puede personalizar mediante el icono dedicado. Obtenga más información sobre los campos de personalización en [esta sección](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Para obtener más información sobre la gestión de correo rechazado, consulte [esta sección](delivery-failures.md#bounce-mail-management).

## Habilitar cancelación de suscripción a una lista de un clic {#one-click-list-unsubscribe}

La URL de cancelación de suscripción a una lista de un clic es un vínculo o botón que se muestra junto a la información del remitente del correo electrónico, lo que permite a los destinatarios excluirse instantáneamente de sus listas de correo con un solo clic. <!--[Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=es#list-unsubscribe){target="_blank"}-->

Se muestra como un vínculo **Cancelar la suscripción** en las interfaces de correo electrónico de los ISP. Por ejemplo:

![](assets/email-list-unsubscribe-example.png)

Añadir un encabezado SMTP denominado List-Unsubscribe es obligatorio para garantizar una gestión óptima de la entrega, y se puede utilizar como alternativa al icono &quot;Notificar como correo no deseado&quot;. De hecho, el uso de esta funcionalidad reduce las tasas de quejas y ayuda a proteger su reputación.

>[!IMPORTANT]
>
>Para mostrar la URL &quot;Cancelar la suscripción&quot; con un solo clic en el encabezado del correo electrónico, el cliente de correo electrónico de los destinatarios debe admitir esta función.

Para habilitar esta funcionalidad, seleccione la opción **[!UICONTROL Addition of One-click List-Unsubscription Header]** en la pestaña **[!UICONTROL SMTP]** de las propiedades de entrega.

>[!NOTE]
>
>Esta opción está habilitada de manera predeterminada.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

Según el cliente de correo electrónico y el método que utilice para realizar la exclusión, hacer clic en el vínculo **Cancelar suscripción** del encabezado del correo electrónico puede tener el siguiente impacto:

* Si el cliente de correo electrónico utiliza el método de cancelación de suscripción a una lista de **un clic**, el destinatario se excluye directamente.

  >[!NOTE]
  >
  >Los principales ISP, como Google y Yahoo! están exigiendo a los remitentes que cumplan con **Cancelación de suscripción a una lista de un clic**.

* Si el cliente de correo electrónico no admite la cancelación de la suscripción a una lista de un clic, puede seguir utilizando el método de cancelación de suscripción a una lista **&quot;mailto&quot;**, que envía un correo electrónico rellenado previamente a la dirección de cancelación de suscripción especificada en el encabezado del correo electrónico.

  Puede establecer la dirección explícitamente en el encabezado o utilizar una dirección dinámica (por ejemplo, utilizando &lt;%=errorAddress%> o la opción &quot;NmsEmail_DefaultErrorAddress&quot;) que se puede configurar mediante el asistente de implementación.

>[!NOTE]
>
>También puede establecer manualmente los métodos [One-Click List-Unsubscribe](https://experienceleague.adobe.com/es/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} y [&quot;mailto&quot; List-Unsubscribe](https://experienceleague.adobe.com/es/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"}. Los pasos detallados se describen en la [Guía de prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=es#list-unsubscribe){target="_blank"} de Experience Cloud.


## Añadir encabezados SMTP {#adding-smtp-headers}

Es posible añadir encabezados SMTP a las entregas. Para ello, utilice la sección correspondiente en la pestaña **[!UICONTROL SMTP]** de la entrega.

El script introducido en esta ventana debe hacer referencia a un encabezado por línea con el siguiente formato **name:value**.

Los valores se codifican automáticamente si es necesario.

>[!IMPORTANT]
>
>La adición de secuencias de comandos para insertar encabezados SMTP se reserva para usuarios avanzados.
>
>La sintaxis de esta secuencia de comandos debe cumplir con los requisitos de este tipo de contenido: no dejar espacios sin utilizar, ninguna línea vacía, etc.

![](assets/email-smtp-headers.png)


## Generar página espejo {#generating-mirror-page}

La página espejo es una página HTML a la que se puede acceder en línea mediante un navegador web. Su contenido es idéntico al del correo electrónico. Puede resultar útil si los destinatarios están experimentando problemas de procesamiento o imágenes rotas al intentar ver el correo electrónico en su bandeja de entrada.

Aprenda a insertar un vínculo a la página espejo de [esta sección](mirror-page.md)
