---
title: Publicar mensajes en Twitter con Adobe Campaign
description: Aprenda a utilizar el módulo Adobe Campaign Social Marketing para publicar mensajes en Twitter y enviar mensajes directos a sus seguidores
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 36%

---


# Publicar mensajes en Twitter con Adobe Campaign {#post-tw-messages}

Adobe Campaign incluye un **Marketing social** que le permite interactuar con sus clientes y clientes potenciales a través de Twitter.

Una vez configurada la integración, puede:

* Enviar mensajes en Twitter: Adobe Campaign le permite enviar mensajes directos a sus seguidores.
* Publicar tweets: use Adobe Campaign para publicar tweets en su cuenta de Twitter.
* Recopile nuevos contactos: Adobe Campaign puede recuperar automáticamente los datos de perfil, lo que le permite llevar a cabo campañas de objetivos y, cuando sea posible, implementar estrategias multicanal. Esta acción requiere el consentimiento del usuario.

Los pasos de configuración para integrar su cuenta de Twitter con Adobe Campaign se describen en [esta página](../connect/ac-tw.md).

## Crear y publicar una publicación de Twitter {#publish-on-tw}

Siga los pasos a continuación para publicar un mensaje en su cuenta de Twitter:

1. Creación de una entrega de Twitter

   Cree una nueva entrega basada en la plantilla de envíos de **[!UICONTROL Tweet (twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Selección del objetivo principal

   Seleccione las cuentas a las que desee enviar tuits.

   ![](assets/tw-define-target.png)

   1. Haga clic en el vínculo **[!UICONTROL To]**.
   1. Haga clic en el botón **[!UICONTROL Add]**.
   1. Seleccione **[!UICONTROL A Twitter account]**.
   1. En el campo **[!UICONTROL Folder]**, seleccione la carpeta de servicio que contiene la cuenta de Twitter. A continuación, seleccione la cuenta de Twitter a la que desee enviar el tuit.

1. Selección del destino de la prueba

   La pestaña **[!UICONTROL Target of the proofs]** le permite definir la cuenta de Twitter que se utiliza para las entregas de prueba antes de la entrega final.

   Tal y como se detalla en la sección [pasos de configuración](../connect/ac-tw.md#tw-test-account), debe crear una cuenta privada de Twitter de prueba dedicada al envío de pruebas.

   >[!NOTE]
   >
   >Si utiliza la misma cuenta de prueba de Twitter para todas las entregas, puede guardar el objetivo de prueba en la plantilla de entrega de **[!UICONTROL Tweet]**, a la que se accede mediante el nodo **[!UICONTROL Resources > Templates > Delivery templates]**. El objetivo de la prueba se especifica de forma predeterminada para cada nueva entrega.

1. Defina el contenido del anuncio

   Introduzca el contenido del anuncio en la **[!UICONTROL Content]** pestaña .

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Al publicar en Twitter, se aplican las limitaciones:
   >
   >* El mensaje no puede superar los 140 caracteres.
   >* No se admite el formato de HTML.


1. Previsualice la publicación

   Examine la **[!UICONTROL Preview]** para comprobar la renderización del anuncio.

   ![](assets/tw-delivery-preview.png)

   1. Seleccione la pestaña **[!UICONTROL Preview]**.
   1. Haga clic en el menú desplegable **[!UICONTROL Test personalization]** y seleccione **[!UICONTROL Service]**.
   1. En el campo **[!UICONTROL Folder]**, seleccione la carpeta de servicio que contiene su cuenta de Twitter.

1. Envío de una prueba

   Antes de publicar el tweet, asegúrese de validarlo enviando una prueba de la publicación: a continuación, puede obtener una renderización exacta de la publicación en una página de prueba privada de Twitter.

1. Publicar el mensaje

   1. Una vez aprobado el contenido, haga clic en el botón **[!UICONTROL Send]**.
   1. Seleccione **[!UICONTROL Deliver as soon as possible]** y haga clic en el botón **[!UICONTROL Analyze]**.
   1. Una vez finalizado el análisis, compruebe el resultado.
   1. Haga clic en **[!UICONTROL Confirm delivery]**, luego en **[!UICONTROL Yes]**.

## Envío de mensajes directos a los seguidores {#direct-tw-messages}

La variable **[!UICONTROL Synchronize Twitter accounts]** flujo de trabajo técnico recupera la lista de seguidores de Twitter para que pueda enviarles mensajes directos. [Más información](../connect/ac-tw.md#synchro-tw-accounts)

Para enviar mensajes directos a sus seguidores, siga los pasos a continuación:

1. Cree un envío de Twitter basado en la variable **[!UICONTROL Tweet (Direct Message)]** plantilla de envío integrada.

1. Selección del objetivo principal

   ![](assets/tw-dm-define-target.png)

   1. Seleccione el **[!UICONTROL To]** y **[!UICONTROL Add]** botón.

   1. Elija un tipo de objetivo

      * Select **[!UICONTROL Twitter subscribers]** para enviar un mensaje directo a todos sus seguidores.

      * Seleccione **[!UICONTROL Filter conditions]** para definir una consulta y ver su resultado. Obtenga información sobre cómo crear un filtro en [esta sección](../audiences/create-filters.md#advanced-filters).

1. Seleccione el objetivo de la prueba en el **[!UICONTROL Target of the proofs]** pestaña: esta cuenta recibirá la prueba de su mensaje directo.

   Tal y como se detalla en la sección [pasos de configuración](../connect/ac-tw.md#tw-test-account), debe crear una cuenta privada de Twitter de prueba dedicada al envío de pruebas.


   >[!NOTE]
   >
   >Si desea enviar todas las pruebas de mensajes directos a la misma cuenta de Twitter, puede guardar el objetivo de prueba en la variable **[!UICONTROL Tweet (Direct Message)]** plantilla de envío, a la que se accede mediante la variable **[!UICONTROL Resources > Templates > Delivery templates]** nodo .

1. Introduzca el contenido del mensaje en la variable **[!UICONTROL Content]** pestaña .

   ![](assets/tw-dm-content.png)

   Los campos de personalización se pueden usar del mismo modo que para los envíos por correo electrónico, por ejemplo, para agregar el nombre del seguidor en el cuerpo del mensaje. Obtenga más información en [esta sección](../start/create-message.md#personalization).

1. Previsualice el mensaje

   Examine la **[!UICONTROL Preview]** para comprobar la renderización del anuncio.

   ![](assets/tw-dm-preview.png)

   1. Seleccione la pestaña **[!UICONTROL Preview]**.
   1. Haga clic en el menú desplegable **[!UICONTROL Test personalization]** y seleccione **[!UICONTROL Visitor Subscription]**.
   1. Elija una cuenta de Twitter con la que desee probar la vista previa.

1. Envío de una prueba

   Antes de enviar el mensaje, asegúrese de validarlo enviando una prueba a una cuenta de prueba: a continuación, puede obtener una renderización exacta del mensaje en una cuenta privada de Twitter y comprobar el contenido y la personalización.

   ![](../assets/do-not-localize/book.png) [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target=&quot;_blank&quot;}

1. Enviar el mensaje directo

   1. Una vez aprobado el contenido, haga clic en el botón **[!UICONTROL Send]**.
   1. Seleccione **[!UICONTROL Deliver as soon as possible]** y haga clic en el botón **[!UICONTROL Analyze]**.
   1. Una vez finalizado el análisis, compruebe el resultado.
   1. Haga clic en **[!UICONTROL Confirm delivery]**, luego en **[!UICONTROL Yes]**.

>[!CAUTION]
>
>No puede enviar más de 250 mensajes directos al día. Para evitar superar este umbral, puede realizar envíos en olas. Para obtener más información, consulte la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=en#sending-using-multiple-waves){target=&quot;_blank&quot;}.


## Acceso a los datos de seguimiento {#tw-tracking}

En la **[!UICONTROL Tweet]** plantilla de envío, el seguimiento está habilitado de forma predeterminada.

Los datos de seguimiento se pueden ver en los informes de envío y en la **[!UICONTROL Edit > Tracking]** de la entrega y el servicio.

La configuración de seguimiento es la misma que para una entrega de correo electrónico. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=es){target=&quot;_blank&quot;}.

