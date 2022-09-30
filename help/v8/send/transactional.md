---
title: Mensajería transaccional de Campaign
description: Introducción a la mensajería transaccional
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 62%

---

# Introducción a la mensajería transaccional{#send-transactional-messages}

La mensajería transaccional (Centro de Mensajes) es un módulo de Campaign diseñado para gestionar mensajes de activación. Estas notificaciones se generan a partir de eventos activados desde sistemas de información y pueden ser: factura, confirmación de pedido, confirmación de envío, cambio de contraseña, notificación de no disponibilidad del producto, extracto de cuenta, creación de cuenta de sitio web, etc.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support){target=&quot;_blank&quot;} para configurar la mensajería transaccional de Campaign en su entorno.

Los mensajes transaccionales se utilizan para enviar:

* notificaciones, como confirmaciones de pedidos o restablecimientos de contraseña, por ejemplo
* una respuesta individual en tiempo real a una acción del cliente
* contenido no promocional

![](../assets/do-not-localize/glass.png) La configuración de mensajería transaccional se detalla en [esta sección](../config/transactional-msg-settings.md).

![](../assets/do-not-localize/glass.png) Comprenda la arquitectura de mensajería transaccional en [esta página](../architecture/architecture.md#transac-msg-archi).

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

El módulo de Mensajería transaccional de Adobe Campaign está integrado en un sistema de información que devuelve eventos que se deben modificar en mensajes transaccionales personalizados. Estos mensajes se pueden enviar por separado o en serie por correo electrónico, SMS o notificaciones push.

Por ejemplo, imaginemos que es una compañía con un sitio web en el que los clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los clientes que han añadido productos al carro de compras. Cuando uno de ellos abandona el sitio web sin finalizar sus compras (evento externo que activa un evento de Campaign), se les envía automáticamente un correo electrónico de abandono del carro de compras (entrega de mensaje transaccional).

A continuación se detallan los pasos principales para ponerlo en práctica:

1. [Cree un tipo de evento](#create-event-types).
1. [Cree y diseñe la plantilla de mensaje](#create-message-template). Debe vincular un evento al mensaje durante este paso.
1. [Pruebe el mensaje](#test-message-template).
1. [Publique la plantilla de mensaje](#publish-message-template).

Una vez que haya diseñado y publicado la plantilla de mensaje transaccional, si se activa un evento correspondiente, los datos relevantes se envían a Campaign mediante PushEvent y PushEvents [Métodos SOAP](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html){target=&quot;_blank&quot;} y la entrega se envía a los destinatarios objetivo.

## Creación de tipos de eventos {#create-event-types}

Para asegurarse de que cada evento se pueda cambiar a un mensaje personalizado, primero debe crear **tipos de eventos**.

Al [crear una plantilla de mensaje](#create-message-template), debe seleccionar el tipo de evento que coincida con el mensaje que desea enviar.

>[!CAUTION]
>
>Debe crear tipos de eventos antes de poder utilizarlos en plantillas de mensajes.

Para crear tipos de eventos que Adobe Campaign procesará, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Administration > Platform > Enumerations]** del árbol.

1. Seleccione **[!UICONTROL Event type]** en la lista.

1. Haga clic en **[!UICONTROL Add]** para crear un valor de lista desglosada. Puede ser una confirmación de pedido, cambio de contraseña o de envío de pedido, etc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Cada tipo de evento coincide con un valor de la lista desglosada **[!UICONTROL Event type]**.

1. Una vez que se hayan creado los valores de la lista desglosada, cierre la sesión y vuelva a la instancia para que la creación sea eficaz.

>[!NOTE]
>
>Obtenga más información sobre listas desglosadas en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/administration-basics/managing-enumerations.html){target=&quot;_blank&quot;}.

## Definir una plantilla de mensaje transaccional {#create-message-template}

Cada evento puede almacenar en déclencheur un mensaje personalizado. Para que esto suceda, debe crear una plantilla de mensaje que coincida con cada tipo de evento. Las plantillas contienen la información necesaria para personalizar el mensaje transaccional. También puede utilizar plantillas para probar la vista previa del mensaje y enviar pruebas utilizando las direcciones semilla antes de enviar al destinatario final.

### Creación de la plantilla

Para crear una plantilla de mensaje, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Message Center >Transactional message templates]** en el árbol de Adobe Campaign.
1. En la lista de las plantillas de mensajes transaccionales, haga clic con el botón derecho y seleccione **[!UICONTROL New]** en el menú desplegable o haga clic en el botón **[!UICONTROL New]** situado sobre la lista de las plantillas de mensajes transaccionales.

   ![](assets/messagecenter_create_model_001.png)

1. En la ventana de envío, seleccione la plantilla de envío adecuada para el canal que desee utilizar.

   ![](assets/messagecenter_create_model_002.png)

1. Cambie la etiqueta si es necesario.
1. Seleccione el tipo de evento que coincida con el mensaje que desea enviar. Los tipos de eventos que Adobe Campaign va a procesar deben crearse de antemano. [Más información](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >Evite relacionar un tipo de evento a más de una plantilla.

1. Introduzca una naturaleza y una descripción y, a continuación, haga clic en **[!UICONTROL Continue]** para crear el cuerpo del mensaje.

### Creación del contenido{#create-message-content}

La definición del contenido del mensaje transaccional es la misma que para todas las entregas en Adobe Campaign. Por ejemplo, para una entrega de correo electrónico, puede crear contenido en formato HTML o texto, añadir archivos adjuntos o personalizar el objeto de envío. [Más información](../start/create-message.md).

>[!CAUTION]
>
>Las imágenes incluidas en el mensaje deben ser de fácil acceso público. Adobe Campaign no proporciona ningún mecanismo de carga de imágenes para los mensajes transaccionales.\
>A diferencia de JSSP o webApp, `<%=` no tiene ninguna omisión predeterminada.
>
>Debe omitir correctamente todos los datos procedentes del evento. Esta omisión depende de cómo se utilice este campo. Por ejemplo, dentro de una URL, utilice encodeURIComponent. Para mostrar en HTML, puede utilizar escapeXMLString.

Una vez definido el contenido del mensaje, puede integrar la información del evento en el cuerpo del mensaje y personalizarlo. La información del evento se inserta en el cuerpo del texto gracias a las etiquetas de personalización.

![](assets/messagecenter_create_content.png)

* Todos los campos de personalización proceden de la carga útil.
* Es posible hacer referencia a uno o varios bloques de personalización en un mensaje transaccional. <!--The block content will be added to the delivery content during the publication to the execution instance.-->

Para insertar etiquetas de personalización en el cuerpo de un mensaje de correo electrónico, aplique los siguientes pasos:

1. En la plantilla de mensaje, haga clic en la pestaña que coincida con el formato de correo electrónico (HTML o texto).
1. Introduzca el cuerpo del mensaje.
1. En el cuerpo del texto, inserte la etiqueta utilizando los menús **[!UICONTROL Real time events>Event XML]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Complete la etiqueta con la siguiente sintaxis: **element name**.@**attribute name** como se muestra a continuación.

   ![](assets/messagecenter_create_custo_2.png)

## Prueba de la plantilla de mensaje transaccional {#test-message-template}

### Adición de direcciones semilla{#add-seeds}

Una dirección semilla permite mostrar una vista previa del mensaje, enviar una prueba y probar la personalización del mensaje antes de enviarlo. Las direcciones semilla están vinculadas a la entrega y no se pueden utilizar para otros envíos.

1. En la plantilla de mensaje transaccional, haga clic en el botón **[!UICONTROL Seed addresses]** y, a continuación, haga clic en la pestaña **[!UICONTROL Add]** botón.

   ![](assets/messagecenter_create_seed_1.png)

1. Asigne una etiqueta para facilitar la selección más tarde e introduzca la dirección semilla (correo electrónico o teléfono móvil según el canal de comunicación).

1. Introduzca el identificador externo: este campo opcional permite introducir una clave comercial (ID única, nombre + correo electrónico, etc.) que es común a todas las aplicaciones del sitio web y es utilizada para identificar los perfiles. Si este campo también está presente en la base de datos de marketing de Adobe Campaign, puede conciliar un evento con un perfil de la base de datos.

   ![](assets/messagecenter_create_seed_2.png)

1. Inserte datos de prueba. Consulte [esta sección](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Haga clic en **[!UICONTROL Ok]** para confirmar la creación de la dirección semilla.

1. Repita el proceso para crear todas las direcciones que sean necesarias.

   ![](assets/messagecenter_create_seed_6.png)

Una vez creadas las direcciones, puede acceder a su vista previa y personalización.

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### Previsualizar el mensaje transaccional{#transactional-message-preview}

Una vez que haya creado una o varias direcciones semilla y el cuerpo del mensaje, puede obtener una previsualización del mensaje y comprobar su personalización.

1. En la plantilla del mensaje, haga clic en la **[!UICONTROL Preview]** y, a continuación, seleccione **[!UICONTROL A seed address]** en la lista desplegable .

   ![](assets/messagecenter_preview_1.png)

1. Seleccione la dirección semilla creada anteriormente para mostrar el mensaje personalizado.

   ![](assets/messagecenter_create_seed_7.png)

### Envío de una prueba

Puede probar la entrega de mensajes enviando una prueba a una dirección semilla creada anteriormente.

El envío de una prueba implica realizar el mismo proceso que para cualquier entrega.

![](../assets/do-not-localize/book.png) Obtenga más información sobre las pruebas en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html#sending-a-proof){target=&quot;_blank&quot;}

Sin embargo, para enviar una prueba de un mensaje transaccional, debe realizar las siguientes operaciones:

* Crear una o más [direcciones semilla](#add-seeds) con datos de prueba de personalización
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

## Publicación de la plantilla {#publish-message-template}

Cuando se crea la plantilla de mensaje<!-- on the control instance--> Cuando haya terminado, puede publicarlo, lo que le permitirá enviar mensajes vinculados a eventos en tiempo real y por lotes.

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>Siempre que realice cambios en una plantilla, asegúrese de publicarla de nuevo para que estos cambios sean efectivos durante el envío del mensaje transaccional.

1. Vaya a la carpeta **[!UICONTROL Message Center > Transactional message templates]** del árbol.
1. Seleccione la plantilla que desee publicar<!--on your execution instances-->.
1. Haga clic en **[!UICONTROL Publish]**.

   ![](assets/messagecenter_publish_template.png)

Una vez finalizada la publicación, las dos plantillas de mensaje que se aplican a los eventos de tipo por lote y en tiempo real se crean en la variable **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** carpeta.

![](assets/messagecenter_deployed_model.png)

Una vez publicada la plantilla, si se activa el evento correspondiente, Adobe Campaign<!--execution instance--> recibirá el evento, lo vinculará a la plantilla transaccional y enviará el mensaje transaccional correspondiente a cada destinatario.

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## Cancelar la publicación de una plantilla

Una vez publicada la plantilla de mensaje <!--on the execution instances-->, se puede cancelar la publicación.

* De hecho, se puede seguir llamando a una plantilla publicada si se activa el evento correspondiente: si ya no utiliza una plantilla de mensaje, se recomienda cancelar la publicación. Esto es para evitar enviar un mensaje transaccional no deseado por error.

   Por ejemplo, ha publicado una plantilla de mensaje que solo utiliza para campañas de Navidad. Tal vez quiera cancelar la publicación después de que termine el período de Navidad y publicarla nuevamente el año que viene.

* Tampoco puede eliminar una plantilla de mensaje transaccional que tenga el estado **[!UICONTROL Published]**. Primero debe cancelar la publicación.

Para cancelar la publicación de una plantilla de mensaje transaccional, siga los pasos a continuación.

1. Examine la carpeta **[!UICONTROL Message Center > Transactional message templates]**.
1. Seleccione la plantilla para cancelar la publicación.
1. Haga clic **[!UICONTROL Unpublish]**.
1. Haga clic **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

El estado de la plantilla de mensaje transaccional cambia de **[!UICONTROL Published]** a **[!UICONTROL Being edited]**.

Una vez finalizada la cancelación de la publicación:

* Ambas plantillas de mensaje (aplicadas a eventos de tipo por lotes y en tiempo real) se eliminan<!-- from each execution instance-->.

   Ya no aparecen en la carpeta **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**.

* Una vez cancelada la publicación de una plantilla, puede eliminarla<!-- from the control instance-->.

   Para ello, selecciónela en la lista y haga clic en el botón **[!UICONTROL Delete]** situado en la parte superior derecha de la pantalla.
