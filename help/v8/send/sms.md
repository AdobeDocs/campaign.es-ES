---
product: Adobe Campaign
title: Enviar SMS con Adobe Campaign
description: Introducción a SMS en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: e65750c4e9ebd0367f0430455cac2cc6502ade7e
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 16%

---

# Crear y enviar SMS

Utilice Adobe Campaign para enviar mensajes SMS personalizados.

[!DNL :arrow_upper_right:] Obtenga información sobre cómo empezar a utilizar el canal SMS en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html)

>[!NOTE]
>
>Adobe Campaign también permite enviar notificaciones push a móviles mediante su opción **Adobe Campaign Mobile App Channel (NMAC)**. Obtenga más información en [esta sección](push.md).

## Configuración del canal de SMS

Para enviar a un teléfono móvil, necesita:

* una cuenta externa que especifique un conector y el tipo de mensaje.

* Una plantilla de envíos en la que se haga referencia a esta cuenta externa.

!DNL :arrow_upper_right:] Obtenga información sobre cómo configurar un canal SMS en [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages)

Antes de comenzar a enviar mensajes SMS:

* Asegúrese de que los perfiles de los destinatarios contengan al menos un teléfono móvil en su perfil.
* Revise las [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages) de Adobe Campaign Classic que también se aplican a Campaign v8.

Además, debe estar familiarizado con el protocolo y la configuración SMS. Consulte la configuración de conexión entre Adobe Campaign y un proveedor SMPP en [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages).

## Creación de su primer envío de SMS

1. Para crear un nuevo envío, vaya a la pestaña **[!UICONTROL Campaigns]** , haga clic en **[!UICONTROL Deliveries]** y haga clic en el botón **[!UICONTROL Create]** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] Para obtener información global sobre cómo crear una entrega, consulte la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages).

1. Seleccione una plantilla de envío que haga referencia a la cuenta externa correspondiente para enviar envíos SMS.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] Obtenga información sobre cómo crear una cuenta externa SMPP en la documentación de  [Campaign Classic v7](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account)

   [!DNL :arrow_upper_right:] Aprenda a crear una plantilla de envío para entregarla a móviles en la documentación de  [Campaign Classic v7](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template)

1. Identifique su entrega con una etiqueta, un código y una descripción.

1. Haga clic en **[!UICONTROL Continue]** para confirmar y mostrar la ventana de configuración de mensajes.

1. Introduzca el contenido del mensaje en la sección **[!UICONTROL Text content]** del asistente, incluidos los campos de personalización según sea necesario.

   ![](assets/sms-content.png)

1. Selección de la población objetivo.

Los pasos clave para crear y diseñar un SMS se detallan en la documentación de Campaign Classic v7 :

* Creación de un SMS

   [!DNL :arrow_upper_right:] [Obtenga información sobre cómo crear un envío de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)

* Diseño del contenido del SMS

   [!DNL :arrow_upper_right:] [Aprenda a definir el contenido del SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)

* Seleccione la audiencia del correo electrónico

   [!DNL :arrow_upper_right:] [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

[!DNL :bulb:] Los pasos para definir una audiencia se detallan en  [esta página](../start/audiences.md).

## Pruebe su SMS

Para ver la renderización del mensaje con su personalización, haga clic en **[!UICONTROL Preview]** y seleccione un destinatario.

![](assets/sms-preview.png)

Para enviar una prueba, consulte estas secciones de la documentación de Campaign Classic v7 :

* Validación de una entrega y envío de pruebas
   [!DNL :arrow_upper_right:] [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Adición de direcciones semilla
   [!DNL :arrow_upper_right:] [Más información sobre las direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Envío y monitorización de envíos SMS

Los pasos clave para enviar y supervisar un SMS se detallan en la documentación de Campaign Classic v7 :

* Envío, monitorización y seguimiento de envíos de SMS

   [!DNL :arrow_upper_right:] [Obtenga información sobre las herramientas para enviar, supervisar y rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)
* Solución de problemas de envíos de SMS

   [!DNL :arrow_upper_right:] [Obtenga información sobre la resolución de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)
