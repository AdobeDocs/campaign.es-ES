---
title: Envío de SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 18%

---

# Creación y envío de SMS

Utilice Adobe Campaign para enviar mensajes SMS personalizados.

Obtenga información sobre cómo empezar a usar el canal SMS en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target="_blank"}

>[!NOTE]
>
>Adobe Campaign también le permite enviar notificaciones push a los móviles a través de su opción **Adobe Campaign Mobile App Channel (NMAC)**. Obtenga más información en [esta sección](push.md).

## Configuración del canal de SMS

Para enviar a un teléfono móvil, necesita:

* una cuenta externa que especifique un conector y el tipo de mensaje.

* Una plantilla de envíos en la que se haga referencia a esta cuenta externa.

Obtenga información sobre cómo configurar un canal SMS en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

Antes de comenzar a enviar mensajes SMS:

* Asegúrese de que los perfiles de los destinatarios contengan al menos un teléfono móvil en su perfil.
* Revise las [prácticas recomendadas de entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=es#sending-messages){target="_blank"} de Adobe Campaign Classic, que también se aplican a la versión 8 de Campaign.

Además, debe estar familiarizado con el protocolo y la configuración de SMS. Consulte la configuración de conexión entre Adobe Campaign y un proveedor SMPP en [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## Creación de su primer envío de SMS

1. Para crear una entrega nueva, vaya a la pestaña **[!UICONTROL Campaigns]**, haga clic en **[!UICONTROL Deliveries]** y luego en el botón **[!UICONTROL Create]** situado sobre la lista de entregas existentes.

   ![](assets/delivery_step_1.png)

   Para obtener información general sobre cómo crear un envío, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. Seleccione una plantilla de envío que haga referencia a la cuenta externa correspondiente para realizar envíos SMS.

   ![](assets/sms-template-list.png)

   Aprenda a crear una cuenta externa SMPP en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   Aprenda a crear una plantilla de envíos para enviarlos a móviles en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. Identifique su envío con una etiqueta, un código y una descripción.

1. Haga clic en **[!UICONTROL Continue]** para confirmar y mostrar la ventana de configuración de mensajes.

1. Introduzca el contenido del mensaje en la sección **[!UICONTROL Text content]** del asistente, incluidos los campos de personalización según sea necesario.

   ![](assets/sms-content.png)

1. Seleccione la población objetivo.

Los pasos clave para crear y diseñar un SMS se detallan en la documentación de Campaign Classic v7:

* Creación de un SMS

  [Aprenda a crear un envío de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* Diseño del contenido del SMS

  [Aprenda a definir el contenido del SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* Seleccione la audiencia del correo electrónico

  [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

Los pasos para definir una audiencia se detallan en [esta página](../start/audiences.md).

## Prueba de SMS

Para ver la renderización del mensaje con su personalización, haga clic en **[!UICONTROL Preview]** y seleccione un destinatario.

![](assets/sms-preview.png)

Para enviar una prueba, consulte estas secciones de la documentación de Campaign Classic v7:

* Validación de una entrega y envío de pruebas
  [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target="_blank"}
* Adición de direcciones semilla
  [Más información sobre las direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Envío y monitorización de envíos de SMS

Los pasos clave para enviar y monitorizar un SMS se detallan en la documentación de Campaign Classic v7:

* Envío, monitorización y seguimiento de entregas de SMS

  [Obtenga información acerca de las herramientas para enviar, supervisar y rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* Solución de problemas de envíos SMS

  [Más información sobre la solución de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
