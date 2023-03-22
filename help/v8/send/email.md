---
title: Envío de correos electrónicos con Adobe Campaign
description: Introducción a los correos electrónicos en Adobe Campaign. Envíe correos electrónicos personalizados a un público objetivo.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 4c79078e32c77499f15906fc81f31ce2b26559d7
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 29%

---

# Diseño y envío de correos electrónicos

Los envíos de correo electrónico le permiten enviar correos electrónicos personalizados a la población objetivo.

![](../assets/do-not-localize/book.png) Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html){target="_blank"}

## Creación de la primera entrega de correo electrónico

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

![](assets/new-email-content.png)


En el siguiente ejemplo, aprenderá los pasos para diseñar una entrega por correo electrónico en Adobe Campaign que contenga datos personalizados, vínculos a una URL externa y un vínculo a la página espejo.

1. **Creación de la entrega**

   Para crear un nuevo envío, vaya a la **Campañas** , haga clic en **Entregas** y haga clic en el botón **Crear** situado encima de la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

1. **Seleccione la plantilla**

   Seleccione una plantilla de envío y asigne un nombre a la entrega. Este nombre solo está visible para los usuarios de la consola de Adobe Campaign y no para los destinatarios. Sin embargo, este título se muestra en la lista de envíos. Haga clic en **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importar el contenido**

   Haga clic en el **Fuente** para pegar el contenido del HTML.

   ![](assets/paste-content.png)


1. **Personalización del mensaje**

   * Añadir el nombre y los apellidos de los destinatarios

      Para insertar el nombre y los apellidos de los perfiles de destino en el contenido del mensaje, coloque el cursor donde desee insertarlos y haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL Greetings]**.

      ![](assets/include-greetings.png)

      Vaya a la pestaña Preview para comprobar la personalización seleccionando un destinatario.

      ![](assets/perso-check.png)

      Obtenga más información sobre las opciones de personalización en [esta sección](personalize.md).

   * Inserción de un vínculo rastreado

      Para transferir los destinatarios de envíos a una dirección externa a través de una imagen o un texto, selecciónelos y haga clic en el botón **[!UICONTROL Add a link]** en la barra de herramientas.

      Introduzca la dirección URL del vínculo en el campo **URL** con el formato **https://www.myURL.com** y, a continuación, confirme la acción.

      ![](assets/add-a-link.png)

   * Adición de una página espejo

      Para permitir a los destinatarios ver el contenido de su envío en un navegador web, añada un vínculo a la [página espejo](../send/mirror-page.md) del mensaje.

      Sitúe el cursor donde desee insertar este vínculo, haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL link to mirror page]**.
   Una vez que el contenido esté listo, haga clic en **Guardar**: ahora se muestra en la lista de envíos, en la variable **[!UICONTROL Campaigns > Deliveries]** pestaña . Su primer envío de correo electrónico está listo. Ahora debe definir la audiencia, validar la entrega y enviarlo.


Obtenga información sobre cómo importar contenido de correo electrónico en [caso de uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

Obtenga más información en estas secciones de **Documentación de Campaign Classic v7**:

* Diseño de un correo electrónico en Campaign
   ![](../assets/do-not-localize/book.png) [Aprenda a diseñar un correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=es){target="_blank"}
* Creación y uso de una plantilla de correo electrónico
   ![](../assets/do-not-localize/book.png) [Más información acerca de las plantillas de correo electrónico](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=es){target="_blank"}
* Seleccione la audiencia del correo electrónico
   ![](../assets/do-not-localize/book.png) [Obtenga información sobre cómo definir la población objetivo](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}
* Validación de una entrega y envío de pruebas
   ![](../assets/do-not-localize/book.png) [Conozca los pasos clave para validar una entrega](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target="_blank"}
* Agregar [direcciones semilla](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}

## Comprobación y validación de los correos electrónicos

Campaign ofrece varias formas de probar y validar los correos electrónicos antes de enviarlos a las audiencias. Obtenga información sobre cómo previsualizar y probar el contenido de su correo electrónico en [esta página](../send/preview-and-proof.md).

Puede hacer lo siguiente:

* Comprobar registros de análisis de envío
* Envío de pruebas
* Adición de direcciones semilla
* Uso de grupos de control

![](../assets/do-not-localize/book.png) [Obtenga más información en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=es){target="_blank"}
