---
product: Adobe Campaign
title: Enviar SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 16%

---

# Crear y enviar SMS

Utilice Adobe Campaign para enviar mensajes SMS personalizados.

[!DNL :arrow_upper_right:] Obtenga información sobre cómo empezar a usar el canal SMS en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>Adobe Campaign también permite enviar notificaciones push a móviles mediante su opción **Adobe Campaign Mobile App Channel (NMAC)**. Obtenga más información en [esta sección](push.md).

## Configuración del canal de SMS

Para enviar a un teléfono móvil, necesita:

* una cuenta externa que especifique un conector y el tipo de mensaje.

* Una plantilla de envíos en la que se haga referencia a esta cuenta externa.

[!DNL :arrow_upper_right:]  Aprenda a configurar un canal SMS en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

Antes de comenzar a enviar mensajes SMS:

* Asegúrese de que los perfiles de los destinatarios contengan al menos un teléfono móvil en su perfil.
* Revise las [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;} de Adobe Campaign Classic que también se aplican a Campaign v8.

Además, debe estar familiarizado con el protocolo y la configuración SMS. Consulte la configuración de conexión entre Adobe Campaign y un proveedor SMPP en [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## Creación de su primer envío de SMS

1. Para crear un nuevo envío, vaya a la pestaña **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** y haga clic en el botón **[!UICONTROL Create]** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] Para obtener información global sobre cómo crear una entrega, consulte la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. Seleccione una plantilla de envío que haga referencia a la cuenta externa correspondiente para enviar envíos SMS.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] Aprenda a crear una cuenta externa SMPP en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   [!DNL :arrow_upper_right:] Aprenda a crear una plantilla de envío para enviarla a móviles en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. Identifique su entrega con una etiqueta, un código y una descripción.

1. Haga clic en **[!UICONTROL Continue]** para confirmar y mostrar la ventana de configuración de mensajes.

1. Introduzca el contenido del mensaje en la sección **[!UICONTROL Text content]** del asistente, incluidos los campos de personalización según sea necesario.

   ![](assets/sms-content.png)

1. Selección de la población objetivo.

Los pasos clave para crear y diseñar un SMS se detallan en la documentación de Campaign Classic v7 :

* Creación de un SMS

   [!DNL :arrow_upper_right:] [Aprenda a crear un envío SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Diseño del contenido del SMS

   [!DNL :arrow_upper_right:] [Aprenda a definir el contenido del SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Seleccione la audiencia del correo electrónico

   [!DNL :arrow_upper_right:] [Aprenda a definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

[!DNL :bulb:] Los pasos para definir una audiencia se detallan en  [esta página](../start/audiences.md).

## Pruebe su SMS

Para ver la renderización del mensaje con su personalización, haga clic en **[!UICONTROL Preview]** y seleccione un destinatario.

![](assets/sms-preview.png)

Para enviar una prueba, consulte estas secciones de la documentación de Campaign Classic v7 :

* Validación de una entrega y envío de pruebas
   [!DNL :arrow_upper_right:] [Conozca los pasos clave para validar un envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Adición de direcciones semilla
   [!DNL :arrow_upper_right:] [Obtenga información sobre las direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## Envío y monitorización de envíos SMS

Los pasos clave para enviar y supervisar un SMS se detallan en la documentación de Campaign Classic v7 :

* Envío, monitorización y seguimiento de envíos de SMS

   [!DNL :arrow_upper_right:] [Obtenga información sobre las herramientas para enviar, supervisar y rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Solución de problemas de envíos de SMS

   [!DNL :arrow_upper_right:] [Obtenga información sobre la solución de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
