---
title: Campaign Transactional messaging
description: Get started with Transactional messaging
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: ec044d6176b4d00302d7a7e24520b97669bede49
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 71%

---

# Get Started with Transactional messaging{#send-transactional-messages}

La mensajería transaccional (Centro de Mensajes) es un módulo de Campaign diseñado para gestionar mensajes de activación. These notifications are generated from events triggered from information systems, and can be: invoice, order confirmation, shipping confirmation, password change, product unavailability notification, account statement, website account creation, etc.

![](../assets/do-not-localize/speech.png)[](../start/campaign-faq.md#support)

Transactional messages are used to send:

* notifications, such as order confirmations or password resets for example
* an individual real-time response to a customer action
* non-promotional content

![](../assets/do-not-localize/glass.png)[](../config/transactional-msg-settings.md)

![](../assets/do-not-localize/glass.png)[](../architecture/architecture.md)

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

El módulo de Mensajería transaccional de Adobe Campaign está integrado en un sistema de información que devuelve eventos que se deben modificar en mensajes transaccionales personalizados. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

Por ejemplo, imaginemos que es una compañía con un sitio web en el que los clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los clientes que han añadido productos al carro de compras. Cuando uno de ellos abandona el sitio web sin finalizar sus compras (evento externo que activa un evento de Campaign), se les envía automáticamente un correo electrónico de abandono del carro de compras (entrega de mensaje transaccional).

The main steps for putting this into place are detailed below:

1. [Cree un tipo de evento](#create-event-types).
1. [Cree y diseñe la plantilla de mensaje](#create-message-template). Debe vincular un evento al mensaje durante este paso.
1. [Pruebe el mensaje](#test-message-template).
1. [Publique la plantilla de mensaje](#publish-message-template).

[](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html)

## Creación de tipos de eventos {#create-event-types}

Para asegurarse de que cada evento se pueda cambiar a un mensaje personalizado, primero debe crear **tipos de eventos**.

Al [crear una plantilla de mensaje](#create-message-template), debe seleccionar el tipo de evento que coincida con el mensaje que desea enviar.

>[!IMPORTANT]
>
>Debe crear tipos de eventos antes de poder utilizarlos en plantillas de mensajes.

Para crear tipos de eventos que Adobe Campaign procesará, siga los pasos a continuación:

1. Inicie sesión en la **instancia de control**.

1. Vaya a la carpeta **[!UICONTROL Administration > Platform > Enumerations]** del árbol.

1. Seleccione **[!UICONTROL Event type]** en la lista.

1. Haga clic en **[!UICONTROL Add]** para crear un valor de lista desglosada. Puede ser una confirmación de pedido, cambio de contraseña o de envío de pedido, etc.

   <!--![](assets/messagecenter_eventtype_enum_001.png)-->

   >[!IMPORTANT]
   >
   >Cada tipo de evento coincide con un valor de la lista desglosada **[!UICONTROL Event type]**.

1. Una vez que se hayan creado los valores de la lista desglosada, cierre la sesión y vuelva a la instancia para que la creación sea eficaz.

>[!NOTE]
>
>[](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html)

## Define a transactional message template {#create-message-template}

Each event can trigger a a personalized message. For this to happen, you need to create a message template to match each event type. Las plantillas contienen la información necesaria para personalizar el mensaje transaccional. También puede utilizar plantillas para probar la vista previa del mensaje y enviar pruebas utilizando las direcciones semilla antes de enviar al destinatario final.

### Create the template

To create a message template, follow the steps below:

1. Vaya a la carpeta **[!UICONTROL Message Center >Transactional message templates]** en el árbol de Adobe Campaign.
1. En la lista de las plantillas de mensajes transaccionales, haga clic con el botón derecho y seleccione **[!UICONTROL New]** en el menú desplegable o haga clic en el botón **[!UICONTROL New]** situado sobre la lista de las plantillas de mensajes transaccionales.

   ![](assets/messagecenter_create_model_001.png)

1. En la ventana de envío, seleccione la plantilla de envío adecuada para el canal que desee utilizar.

   ![](assets/messagecenter_create_model_002.png)

1. Cambie la etiqueta si es necesario.
1. Seleccione el tipo de evento que coincida con el mensaje que desea enviar.

   ![](assets/messagecenter_create_model_003.png)

   Event types destined to be processed by Adobe Campaign must be created beforehand.

   >[!CAUTION]
   >
   >Evite relacionar un tipo de evento a más de una plantilla.

1. **[!UICONTROL Continue]** [](#create-message-content)

### Create the content{#create-message-content}

The definition of the transactional message content is the same as for all deliveries in Adobe Campaign. Por ejemplo, para una entrega de correo electrónico, puede crear contenido en formato HTML o texto, añadir archivos adjuntos o personalizar el objeto de envío. Para obtener más información, consulte [esta sección](../start/create-message.md).

>[!CAUTION]
>
>Las imágenes incluidas en el mensaje deben ser de fácil acceso público. Adobe Campaign no proporciona ningún mecanismo de carga de imágenes para los mensajes transaccionales.\
>A diferencia de JSSP o webApp, `<%=` no tiene ninguna omisión predeterminada.
>
>You have to escape each data coming from the event properly. Esta omisión depende de cómo se utilice este campo. Por ejemplo, dentro de una URL, utilice encodeURIComponent. Para mostrar en HTML, puede utilizar escapeXMLString.

Una vez definido el contenido del mensaje, puede integrar la información del evento en el cuerpo del mensaje y personalizarlo. La información del evento se inserta en el cuerpo del texto gracias a las etiquetas de personalización.

![](assets/messagecenter_create_content.png)

* Todos los campos de personalización proceden de la carga útil.
* Es posible hacer referencia a uno o varios bloques de personalización en un mensaje transaccional. El contenido del bloque se agrega al contenido de la envío durante la publicación en la instancia de ejecución.

Para insertar etiquetas de personalización en el cuerpo de un mensaje de correo electrónico, aplique los siguientes pasos:

1. En la plantilla de mensaje, haga clic en la pestaña que coincida con el formato de correo electrónico (HTML o texto).
1. Introduzca el cuerpo del mensaje.
1. En el cuerpo del texto, inserte la etiqueta utilizando los menús **[!UICONTROL Real time events>Event XML]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Complete la etiqueta con la siguiente sintaxis: **element name**.@**attribute name** como se muestra a continuación.

   ![](assets/messagecenter_create_custo_2.png)

## Test the transactional message template {#test-message-template}

### Adición de direcciones semilla{#add-seeds}

A seed address lets you display a preview of your message, send a proof, and test message personalization before sending the message. Las direcciones semilla están vinculadas a la entrega y no se pueden utilizar para otros envíos.

1. **[!UICONTROL Seed addresses]****[!UICONTROL Add]**

   ![](assets/messagecenter_create_seed_1.png)

1. Assign a label to it for easy selection later, then enter the seed address (email or mobile phone depending on the communication channel).

1. Introduzca el identificador externo: este campo opcional permite introducir una clave comercial (ID única, nombre + correo electrónico, etc.) que es común a todas las aplicaciones del sitio web y es utilizada para identificar los perfiles. Si este campo también está presente en la base de datos de marketing de Adobe Campaign, puede conciliar un evento con un perfil de la base de datos.

   ![](assets/messagecenter_create_seed_2.png)

1. Insert test data. Consulte [esta sección](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. **[!UICONTROL Ok]**

1. Repita el proceso para crear todas las direcciones que sean necesarias.

   ![](assets/messagecenter_create_seed_6.png)

Once the addresses are created, you can access their preview and personalization.

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. ****

La finalidad de estos datos es probar los mensajes antes de la entrega final. Estos mensajes no coinciden con los datos reales que procesa el Centro de mensajería. Sin embargo, la estructura XML debe ser idéntica a la del evento almacenado en la instancia de ejecución, como se muestra a continuación.

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. En la plantilla del mensaje, haga clic en la pestaña **[!UICONTROL Seed addresses]**.
1. En el contenido del evento, introduzca la información de prueba en formato XML.

   ![](assets/messagecenter_create_custo_3.png)

### Preview your transactional message{#transactional-message-preview}

Una vez que haya creado una o varias direcciones semilla y el cuerpo del mensaje, puede obtener una previsualización del mensaje y comprobar su personalización.

1. **[!UICONTROL Preview]****[!UICONTROL A seed address]**

   ![](assets/messagecenter_preview_1.png)

1. Seleccione la dirección semilla creada anteriormente para mostrar el mensaje personalizado.

   ![](assets/messagecenter_create_seed_7.png)

### Envío de una prueba

Puede probar la entrega de mensajes enviando una prueba a una dirección semilla creada anteriormente.

Sending a proof involves the same process as for any delivery.

![](../assets/do-not-localize/book.png)[](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es)

However, to send a proof of a transactional message, you need to carry out the following operations:

* [](#add-seeds)
* Creación del contenido del mensaje

Para enviar la prueba:

1. Haga clic en el botón **[!UICONTROL Send a proof]** de la ventana envío.
1. Analice la entrega.
1. Corrija los errores y confirme la entrega.

   ![](assets/messagecenter_send_proof_001.png)

1. Compruebe que el mensaje se haya enviado a la dirección semilla y que su contenido cumpla con su configuración.

   ![](assets/messagecenter_send_proof_002.png)

Se puede acceder a las pruebas en cada plantilla a través de la pestaña **[!UICONTROL Audit]**.

![](assets/messagecenter_send_proof_003.png)

## Publish the template {#publish-message-template}

Cuando la plantilla de mensaje creada en la instancia de control esté completa, puede publicarla. Este proceso también lo publicará en todas las instancias de ejecución.

>[!NOTE]
>
>Al publicar plantillas de mensaje transaccional, las reglas de tipología se publican automáticamente en las instancias de ejecución.

La publicación permite crear automáticamente dos plantillas de mensajes en la instancia de ejecución, lo que permite enviar mensajes relacionados con los eventos en tiempo real y por lotes.

>[!CAUTION]
>
>Siempre que realice cambios en una plantilla, asegúrese de publicarla de nuevo para que estos cambios sean efectivos durante el envío del mensaje transaccional.

1. En la instancia de control, vaya a la carpeta **[!UICONTROL Message Center > Transactional message templates]** del árbol.
1. Seleccione la plantilla que desee publicar en las instancias de ejecución.
1. Haga clic **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Una vez terminada la publicación, las dos plantillas de mensaje que se aplican a los eventos de tipo por lote y en tiempo real se crean en el árbol de la instancia de producción de la carpeta **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]**.

![](assets/messagecenter_deployed_model.png)

Una vez publicada una plantilla, si se activa el evento correspondiente, la instancia de ejecución recibirá el evento, lo vinculará a la plantilla transaccional y enviará el mensaje transaccional correspondiente a cada destinatario.

>[!NOTE]
>
>Si se sustituye un campo existente de la plantilla de mensaje transaccional, como la dirección del remitente, con un valor vacío, el campo correspondiente de la(s) instancia(s) de ejecución no se actualizará una vez que se vuelva a publicar el mensaje transaccional. Aún contendrá el valor anterior.
>
>Sin embargo, si se agrega un valor no vacío, el campo correspondiente se actualiza de la forma habitual después de la siguiente publicación.

## Unpublish a template

Una vez publicada una plantilla de mensaje en las instancias de ejecución, se puede cancelar su publicación.

* De hecho, se puede seguir llamando a una plantilla publicada si se activa el evento correspondiente: si ya no utiliza una plantilla de mensaje, se recomienda cancelar la publicación. Esto es para evitar enviar un mensaje transaccional no deseado por error.

   Por ejemplo, ha publicado una plantilla de mensaje que solo utiliza para campañas de Navidad. Tal vez quiera cancelar la publicación después de que termine el período de Navidad y publicarla nuevamente el año que viene.

* Tampoco puede eliminar una plantilla de mensaje transaccional que tenga el estado **[!UICONTROL Published]**. Primero debe cancelar la publicación.

Para cancelar la publicación de una plantilla de mensaje transaccional, siga los pasos a continuación.

1. **[!UICONTROL Message Center > Transactional message templates]**
1. Select the template to unpublish.
1. Haga clic **[!UICONTROL Unpublish]**.
1. Haga clic **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

El estado de la plantilla de mensaje transaccional cambia de **[!UICONTROL Published]** a **[!UICONTROL Being edited]**.

Una vez finalizada la cancelación de la publicación:

* Ambas plantillas de mensaje (aplicadas a eventos de tipo por lotes y en tiempo real) se eliminan de cada instancia de ejecución.

   Ya no aparecen en la carpeta **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**.

* Una vez cancelada la publicación de una plantilla, puede eliminarla de la instancia de control si es necesario.

   Para ello, selecciónela en la lista y haga clic en el botón **[!UICONTROL Delete]** situado en la parte superior derecha de la pantalla.
