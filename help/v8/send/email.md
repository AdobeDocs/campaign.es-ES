---
product: Adobe Campaign
title: Envío de correos electrónicos con Adobe Campaign
description: Introducción a los correos electrónicos en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: d1e96b1311d9de24ceb918230186cd3cad609ab2
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 51%

---

# Diseño y envío de correos electrónicos

Los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo.

[!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Creación de la primera entrega de correo electrónico

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Obtenga información sobre cómo crear una entrega por correo electrónico en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html)


En el siguiente ejemplo, aprenderá los pasos para diseñar una entrega por correo electrónico en Adobe Campaign que contenga datos personalizados, vínculos a una URL externa, un vínculo a la página espejo y un vínculo a un formulario web.

1. Creación de la entrega

   Para crear un nuevo envío, vaya a la pestaña **Campaigns** , haga clic en **Deliveries** y haga clic en el botón **Create** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

1. Seleccione la plantilla

   Seleccione una plantilla de envío y asigne un nombre a la entrega. Este nombre solo está visible para los usuarios de la consola de Adobe Campaign y no para los destinatarios. Sin embargo, este título se muestra en la lista de envíos. Haga clic en **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. Importar el contenido

   Haga clic en la pestaña **Source** para pegar el contenido HTML.

   ![](assets/paste-content.png)


1. Personalización del mensaje


   * Mostrar el nombre completo de los destinatarios

      Para insertar el primer y el segundo nombre de los destinatarios en un campo de texto de su envío, haga clic en el campo de texto seleccionado y, a continuación, coloque el cursor donde desee mostrarlos. Haga clic en el primer icono de la barra de herramientas emergente y, a continuación, haga clic en **[!UICONTROL Personalization block]**. Seleccione **[!UICONTROL Greetings]** y haga clic en **[!UICONTROL OK]**.

   * Inserción de un vínculo en una imagen

      Para transferir los destinatarios de envíos a una dirección externa a través de una imagen, haga clic en la imagen correspondiente para mostrar la barra de herramientas emergente, coloque el cursor en el primer icono y haga clic en **[!UICONTROL Link to an external URL]**.

      Introduzca la dirección URL del vínculo en el campo **URL** con el formato **https://www.myURL.com** y, a continuación, confirme la acción.

      El vínculo se puede cambiar en cualquier momento con la sección a la derecha de la ventana.

   * Inserción de un vínculo en el texto

      Para integrar un vínculo externo en el texto de la entrega, seleccione un texto o un bloque de texto y, a continuación, haga clic en el primer icono de la barra de herramientas emergente. Haga clic en **[!UICONTROL Link to an external URL]** e introduzca la dirección del vínculo en el campo **[!UICONTROL URL]**.

      El vínculo se puede cambiar en cualquier momento con la sección a la derecha de la ventana.

   * Adición de una página espejo

      Para permitir a los destinatarios ver el contenido de la entrega en un navegador web, se puede integrar un vínculo a una página espejo en la entrega.

      Haga clic en el campo de texto en el que desea ver el vínculo publicado. Haga clic en el primer icono de la barra de herramientas emergente, seleccione **[!UICONTROL Personalization block]** y luego **[!UICONTROL Link to Mirror Page (MirrorPage)]**. Haga clic en **[!UICONTROL Save]** para confirmar.

   * Integración de un vínculo a una aplicación web

      El editor de contenido permite integrar vínculos a aplicaciones web desde la consola de Adobe Campaign, como una página de destino o una página de formulario. Para obtener más información, consulte [Vínculo a una aplicación web](../../web/using/editing-content.md#link-to-a-web-application).

      Seleccione un campo de texto para enlazar a una aplicación web y, a continuación, haga clic en el primer icono. Seleccione **[!UICONTROL Link to a Web application]** y luego seleccione la aplicación deseada haciendo clic en el icono situado al final del campo **Web Application**.

1. Envío de mensajes

   Una vez que el contenido esté integrado, guarde la entrega haciendo clic en **Guardar**. A partir de entonces se muestra en la lista de envíos, que se encuentra en la pestaña **[!UICONTROL Campaigns > Deliveries]**.


## Crear contenido y seleccionar la audiencia

Puede crear directamente en Campaign o importar la audiencia, así como el contenido del correo electrónico. Utilice los vínculos siguientes para aprender a:

* Diseño de un correo electrónico en Campaign
   [!DNL :arrow_upper_right:] [Aprenda a diseñar un correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html)
* Importación de contenido de correo electrónico
   [!DNL :arrow_upper_right:] [Caso de uso: Creación de un flujo de trabajo para cargar un contenido de envío](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)
* Creación y uso de una plantilla de correo electrónico
   [!DNL :arrow_upper_right:] [Más información sobre las plantillas de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es)
* Seleccione la audiencia del correo electrónico
   [!DNL :arrow_upper_right:] [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)
* Validación de una entrega y envío de pruebas
   [!DNL :arrow_upper_right:] [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
* Añadir [direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html)

## Comprobación y validación de los correos electrónicos

Campaign ofrece varias formas de probar y validar los correos electrónicos antes de enviarlos a las audiencias.

[!DNL :arrow_upper_right:] [Aplique las prácticas recomendadas enumeradas en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html)

Puede hacer lo siguiente:

* Comprobar registros de análisis de envío
* Envíe pruebas
* Adición de direcciones semilla
* Uso de grupos de control
* Compruebe la renderización del correo electrónico

[!DNL :arrow_upper_right:] [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Supervisión de los correos electrónicos

Una vez enviado, compruebe su estado de envío en el panel de envío y acceda a los registros de envío y a los informes para confirmar que los mensajes se han enviado correctamente.

[!DNL :arrow_upper_right:] [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html)

