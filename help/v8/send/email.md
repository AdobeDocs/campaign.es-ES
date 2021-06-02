---
product: Adobe Campaign
title: Envío de correos electrónicos con Adobe Campaign
description: Introducción a los correos electrónicos en Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: dc99c00f68e53a308f8c869f07aa93baed3a5129
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 15%

---

# Diseño y envío de correos electrónicos

Los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo.

[!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html).

## Creación de la primera entrega de correo electrónico

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

![](assets/new-email-content.png)


En el siguiente ejemplo, aprenderá los pasos para diseñar una entrega por correo electrónico en Adobe Campaign que contenga datos personalizados, vínculos a una URL externa y un vínculo a la página espejo.

1. **Creación de la entrega**

   Para crear un nuevo envío, vaya a la pestaña **Campaigns** , haga clic en **Deliveries** y haga clic en el botón **Create** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

1. **Seleccione la plantilla**

   Seleccione una plantilla de envío y asigne un nombre a la entrega. Este nombre solo está visible para los usuarios de la consola de Adobe Campaign y no para los destinatarios. Sin embargo, este título se muestra en la lista de envíos. Haga clic en **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importar el contenido**

   Haga clic en la pestaña **Source** para pegar el contenido HTML.

   ![](assets/paste-content.png)


1. **Personalización del mensaje**


   * Añadir el nombre y los apellidos de los destinatarios

      Para insertar el nombre y los apellidos de los perfiles de destino en el contenido del mensaje, coloque el cursor donde desee insertarlos, haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Vaya a la pestaña Preview para comprobar la personalización seleccionando un destinatario.

      ![](assets/perso-check.png)

   * Inserción de un vínculo rastreado

      Para transferir los destinatarios de envíos a una dirección externa a través de una imagen o un texto, selecciónelos y haga clic en el icono **[!UICONTROL Add a link]** de la barra de herramientas.

      Introduzca la dirección URL del vínculo en el campo **URL** con el formato **https://www.myURL.com** y, a continuación, confirme la acción.

      ![](assets/add-a-link.png)

   * Adición de una página espejo

      Para permitir a los destinatarios ver el contenido de la entrega en un navegador web, añada un vínculo a la página espejo del mensaje.

      Sitúe el cursor donde desee insertar este vínculo, haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL link to mirror page]**.
   Una vez que el contenido esté listo, haga clic en **Guardar**: ahora se muestra en la lista de envíos, en la pestaña **[!UICONTROL Campaigns > Deliveries]**. Su primer envío de correo electrónico está listo. Ahora debe definir la audiencia, validar la entrega y enviarlo.


Obtenga más información en estas secciones de la documentación de Campaign Classic v7:

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

