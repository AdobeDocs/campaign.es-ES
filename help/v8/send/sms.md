---
title: Enviar SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: SMS
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 20%

---

# Crear y enviar SMS

Utilice Adobe Campaign para enviar mensajes SMS personalizados.

![](../assets/do-not-localize/book.png) Obtenga información sobre cómo empezar a usar el canal SMS en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>Adobe Campaign también permite enviar notificaciones push a móviles mediante sus **Canal de aplicaciones móviles de Adobe Campaign (NMAC)** . Obtenga más información en [esta sección](push.md).

## Configuración del canal de SMS

Para enviar a un teléfono móvil, necesita:

* una cuenta externa que especifique un conector y el tipo de mensaje.

* Una plantilla de envíos en la que se haga referencia a esta cuenta externa.

![](../assets/do-not-localize/book.png)  Obtenga información sobre cómo configurar un canal SMS en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target="_blank"}

Antes de comenzar a enviar mensajes SMS:

* Asegúrese de que los perfiles de los destinatarios contengan al menos un teléfono móvil en su perfil.
* Consulte Adobe Campaign Classic [Prácticas recomendadas relacionadas con las entregas](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target="_blank"} que también se aplican a Campaign v8.

Además, debe estar familiarizado con el protocolo y la configuración SMS. Consulte la configuración de la conexión entre Adobe Campaign y un proveedor SMPP en [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=es#sending-messages){target="_blank"}.

## Creación de su primer envío de SMS

1. Para crear un nuevo envío, vaya a la **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** y haga clic en el botón **[!UICONTROL Create]** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) Para obtener información global sobre cómo crear una entrega, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target="_blank"}.

1. Seleccione una plantilla de envío que haga referencia a la cuenta externa correspondiente para enviar envíos SMS.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Obtenga información sobre cómo crear una cuenta externa SMPP en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target="_blank"}

   ![](../assets/do-not-localize/book.png) Obtenga información sobre cómo crear una plantilla de envío para enviarla a móviles en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target="_blank"}

1. Identifique su entrega con una etiqueta, un código y una descripción.

1. Haga clic en **[!UICONTROL Continue]** para confirmar y mostrar la ventana de configuración de mensajes.

1. Introduzca el contenido del mensaje en la variable **[!UICONTROL Text content]** del asistente, incluidos los campos de personalización según sea necesario.

   ![](assets/sms-content.png)

1. Selección de la población objetivo.

Los pasos clave para crear y diseñar un SMS se detallan en la documentación de Campaign Classic v7 :

* Creación de un SMS

   ![](../assets/do-not-localize/book.png) [Obtenga información sobre cómo crear una entrega SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target="_blank"}

* Diseño del contenido del SMS

   ![](../assets/do-not-localize/book.png) [Aprenda a definir el contenido del SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target="_blank"}

* Seleccione la audiencia del correo electrónico

   ![](../assets/do-not-localize/book.png) [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

![](../assets/do-not-localize/glass.png) Los pasos para definir una audiencia se detallan en [esta página](../start/audiences.md).

## Prueba de SMS

Para ver la renderización del mensaje con su personalización, haga clic en **[!UICONTROL Preview]** y seleccione un destinatario.

![](assets/sms-preview.png)

Para enviar una prueba, consulte estas secciones de la documentación de Campaign Classic v7 :

* Validación de una entrega y envío de pruebas
   ![](../assets/do-not-localize/book.png) [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target="_blank"}
* Adición de direcciones semilla
   ![](../assets/do-not-localize/book.png) [Más información sobre las direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Envío y monitorización de envíos SMS

Los pasos clave para enviar y supervisar un SMS se detallan en la documentación de Campaign Classic v7 :

* Envío, monitorización y seguimiento de entregas de SMS

   ![](../assets/do-not-localize/book.png) [Obtenga información sobre las herramientas para enviar, supervisar y rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target="_blank"}

* Solución de problemas de envíos de SMS

   ![](../assets/do-not-localize/book.png) [Obtenga información sobre la resolución de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target="_blank"}
