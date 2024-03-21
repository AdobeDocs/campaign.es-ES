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
>Adobe Campaign también permite enviar notificaciones push a los móviles a través de su **Canal de aplicaciones móviles de Adobe Campaign (NMAC)** opción. Obtenga más información en [esta sección](push.md).

## Configuración del canal de SMS

Para enviar a un teléfono móvil, necesita:

* una cuenta externa que especifique un conector y el tipo de mensaje.

* Una plantilla de envíos en la que se haga referencia a esta cuenta externa.

Obtenga información sobre cómo configurar un canal SMS en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#sending-messages){target="_blank"}

Antes de comenzar a enviar mensajes SMS:

* Asegúrese de que los perfiles de los destinatarios contengan al menos un teléfono móvil en su perfil.
* Revisión de Adobe Campaign Classic [Prácticas recomendadas de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html#sending-messages){target="_blank"} que también se aplican a Campaign v8.

Además, debe estar familiarizado con el protocolo y la configuración de SMS. Consulte la configuración de conexión entre Adobe Campaign y un proveedor SMPP en [este documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html#sending-messages){target="_blank"}.

## Creación de su primer envío de SMS

1. Para crear un nuevo envío, vaya a **[!UICONTROL Campaigns]** pestaña, haga clic en **[!UICONTROL Deliveries]** y haga clic en **[!UICONTROL Create]** botón situado sobre la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

   Para obtener información general sobre la creación de envíos, consulte [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html#sending-messages){target="_blank"}.

1. Seleccione una plantilla de envío que haga referencia a la cuenta externa correspondiente para realizar envíos SMS.

   ![](assets/sms-template-list.png)

   Obtenga información sobre cómo crear una cuenta externa SMPP en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#creating-an-smpp-external-account){target="_blank"}

   Obtenga información sobre cómo crear una plantilla de envíos para enviarlos a móviles en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html#changing-the-delivery-template){target="_blank"}

1. Identifique su envío con una etiqueta, un código y una descripción.

1. Clic **[!UICONTROL Continue]** para confirmar y mostrar la ventana de configuración de mensajes.

1. Introduzca el contenido del mensaje en la **[!UICONTROL Text content]** del asistente, incluidos los campos de personalización que sean necesarios.

   ![](assets/sms-content.png)

1. Seleccione la población objetivo.

Los pasos clave para crear y diseñar un SMS se detallan en la documentación de Campaign Classic v7:

* Creación de un SMS

  [Obtenga información sobre cómo crear un envío de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#sending-messages){target="_blank"}

* Diseño del contenido del SMS

  [Obtenga información sobre cómo definir el contenido del SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html#defining-the-sms-content){target="_blank"}

* Seleccione la audiencia del correo electrónico

  [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

Los pasos para definir una audiencia se detallan en [esta página](../start/audiences.md).

## Prueba de SMS

Para ver el procesamiento del mensaje con su personalización, haga clic en **[!UICONTROL Preview]** y seleccione un destinatario.

![](assets/sms-preview.png)

Para enviar una prueba, consulte estas secciones de la documentación de Campaign Classic v7:

* Validación de una entrega y envío de pruebas
  [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target="_blank"}
* Adición de direcciones semilla
  [Más información sobre las direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Envío y monitorización de envíos de SMS

Los pasos clave para enviar y monitorizar un SMS se detallan en la documentación de Campaign Classic v7:

* Envío, monitorización y seguimiento de entregas de SMS

  [Obtenga información acerca de las herramientas para enviar, monitorizar y rastrear SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html#sending-messages){target="_blank"}

* Solución de problemas de envíos SMS

  [Obtenga información sobre la resolución de problemas de SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html#sending-messages){target="_blank"}
