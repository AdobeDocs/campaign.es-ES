---
title: Mensajería transaccional de Campaign
description: Introducción a la mensajería transaccional
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 72%

---

# Introducción a la mensajería transaccional{#send-transactional-messages}

La mensajería transaccional (Centro de Mensajes) es un módulo de Campaign diseñado para gestionar mensajes de activación. Estos mensajes se generan a partir de eventos activados desde sistemas de información y pueden ser: una factura, una confirmación de pedido, una confirmación de envío, un cambio de contraseña, una notificación de no disponibilidad del producto, el estado de la cuenta o una creación de cuenta en un sitio web, por ejemplo.

![](../assets/do-not-localize/speech.png)  Como usuario de Cloud Services administrados, [Adobe de contacto](../start/campaign-faq.md#support) para instalar y configurar la mensajería transaccional de Campaign en su entorno.

Los mensajes transaccionales se utilizan para enviar:

* notificaciones, como confirmaciones de pedidos o restablecimientos de contraseña, por ejemplo
* una respuesta individual en tiempo real a una acción del cliente
* contenido no promocional

![](../assets/do-not-localize/glass.png) La configuración de mensajería transaccional se detalla en [esta sección](../config/transactional-msg-settings.md).

![](../assets/do-not-localize/glass.png) Comprenda la arquitectura de mensajería transaccional en [esta página](../dev/architecture.md).

>[!CAUTION]
>
>La mensajería transaccional requiere una licencia específica. Compruebe el acuerdo de licencia.

## Definir plantillas de mensaje transaccional

Cada evento puede almacenar en déclencheur un mensaje personalizado. Para que esto suceda, debe crear una plantilla de mensaje que coincida con cada tipo de evento. Las plantillas contienen la información necesaria para personalizar el mensaje transaccional. También puede utilizar plantillas para probar la vista previa del mensaje y enviar pruebas utilizando las direcciones semilla antes de enviar al destinatario final.

### Creación de la plantilla

Para crear una plantilla de mensaje, siga los pasos a continuación:

1. Vaya a la carpeta **[!UICONTROL Message Center >Transactional message templates]** en el árbol de Adobe Campaign.
1. En la lista de las plantillas de mensajes transaccionales, haga clic con el botón derecho y seleccione **[!UICONTROL New]** en el menú desplegable o haga clic en el botón **[!UICONTROL New]** situado sobre la lista de las plantillas de mensajes transaccionales.

   ![](assets/messagecenter_create_model_001.png)

1. En la ventana de envío, seleccione la plantilla de envío adecuada para el canal que desee utilizar.

   ![](assets/messagecenter_create_model_002.png)

1. Cambie la etiqueta si es necesario.
1. Seleccione el tipo de evento que coincida con el mensaje que desea enviar.

   ![](assets/messagecenter_create_model_003.png)

   Los tipos de eventos que Adobe Campaign va a procesar deben crearse en la instancia de control por Adobe.

   >[!NOTE]
   >
   >Evite relacionar un tipo de evento a más de una plantilla.

1. Introduzca una naturaleza y una descripción y, a continuación, haga clic en **[!UICONTROL Continue]** para crear el cuerpo del mensaje. Consulte [Creación del contenido del mensaje](#create-message-content).

### Creación del contenido{#create-message-content}

La definición del contenido del mensaje transaccional es la misma que para todas las entregas en Adobe Campaign. Por ejemplo, para una entrega de correo electrónico, puede crear contenido en formato HTML o texto, añadir archivos adjuntos o personalizar el objeto de envío. Para obtener más información, consulte [esta sección](../start/create-message.md).

>[!CAUTION]
>
>Las imágenes incluidas en el mensaje deben ser de fácil acceso público. Adobe Campaign no proporciona ningún mecanismo de carga de imágenes para los mensajes transaccionales.\
>A diferencia de JSSP o webApp, `<%=` no tiene ninguna omisión predeterminada.
>
>Debe omitir correctamente todos los datos procedentes del evento. Esta omisión depende de cómo se utilice este campo. Por ejemplo, dentro de una URL, utilice encodeURIComponent. Para mostrar en HTML, puede utilizar escapeXMLString.

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

### Añadir datos de personalización{#personalization-data}

Puede añadir datos en la plantilla de mensaje para probar la personalización del mensaje transaccional. Esto le permite generar una vista previa o enviar una prueba. Si instala la variable **Capacidad de entrega** , estos datos le permiten mostrar un procesamiento de los mensajes para varios clientes de escritorio, web o móviles.

La finalidad de estos datos es probar los mensajes antes de la entrega final. Estos mensajes no coinciden con los datos reales que procesa el Centro de mensajería. Sin embargo, la estructura XML debe ser idéntica a la del evento almacenado en la instancia de ejecución, como se muestra a continuación.

![](assets/messagecenter_create_custo_4.png)

Esta información le permite personalizar el contenido del mensaje mediante etiquetas de personalización.

1. En la plantilla del mensaje, haga clic en la pestaña **[!UICONTROL Seed addresses]**.
1. En el contenido del evento, introduzca la información de prueba en formato XML.

   ![](assets/messagecenter_create_custo_3.png)

### Previsualizar el mensaje transaccional{#transactional-message-preview}

Una vez que haya creado una o varias direcciones semilla y el cuerpo del mensaje, puede obtener una previsualización del mensaje y comprobar su personalización.

1. En la plantilla del mensaje, haga clic en la **[!UICONTROL Preview]** y, a continuación, seleccione **[!UICONTROL A seed address]** en la lista desplegable .

   ![](assets/messagecenter_preview_1.png)

1. Seleccione la dirección semilla creada anteriormente para mostrar el mensaje personalizado.

   ![](assets/messagecenter_create_seed_7.png)

### Envío de una prueba

Puede probar la entrega de mensajes enviando una prueba a una dirección semilla creada anteriormente.

El envío de una prueba implica realizar el mismo proceso que para cualquier entrega.

![](../assets/do-not-localize/book.png) Obtenga más información sobre las pruebas en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target=&quot;_blank&quot;}

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

### Publicación de la plantilla

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


### Cancelar la publicación de una plantilla

Una vez publicada una plantilla de mensaje en las instancias de ejecución, se puede cancelar su publicación.

* De hecho, se puede seguir llamando a una plantilla publicada si se activa el evento correspondiente: si ya no utiliza una plantilla de mensaje, se recomienda cancelar la publicación. Esto es para evitar enviar un mensaje transaccional no deseado por error.

   Por ejemplo, ha publicado una plantilla de mensaje que solo utiliza para campañas de Navidad. Tal vez quiera cancelar la publicación después de que termine el período de Navidad y publicarla nuevamente el año que viene.

* Tampoco puede eliminar una plantilla de mensaje transaccional que tenga el estado **[!UICONTROL Published]**. Primero debe cancelar la publicación.

Para cancelar la publicación de una plantilla de mensaje transaccional, siga los pasos a continuación.

1. En la instancia de control, vaya a la **[!UICONTROL Message Center > Transactional message templates]** carpeta.
1. Seleccione la plantilla para cancelar la publicación.
1. Haga clic **[!UICONTROL Unpublish]**.
1. Haga clic **[!UICONTROL Start]**.

![](assets/message-center-unpublish.png)

El estado de la plantilla de mensaje transaccional cambia de **[!UICONTROL Published]** a **[!UICONTROL Being edited]**.

Una vez finalizada la cancelación de la publicación:

* Ambas plantillas de mensaje (aplicadas a eventos de tipo por lotes y en tiempo real) se eliminan de cada instancia de ejecución.

   Ya no aparecen en la carpeta **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**.

* Una vez cancelada la publicación de una plantilla, puede eliminarla de la instancia de control si es necesario.

   Para ello, selecciónela en la lista y haga clic en el botón **[!UICONTROL Delete]** situado en la parte superior derecha de la pantalla.
