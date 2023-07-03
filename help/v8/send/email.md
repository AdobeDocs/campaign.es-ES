---
title: Envío de correos electrónicos con Adobe Campaign
description: Introducción a los correos electrónicos en Adobe Campaign. Envíe correos electrónicos personalizados a un público objetivo.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 500de76853772313b1aac655da2f1b3562de2c55
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 22%

---

# Diseño y envío de correos electrónicos

Las entregas de correo electrónico permiten enviar correos electrónicos personalizados a la población objetivo. [Más información](../send/send.md)

## Creación de su primer envío de correo electrónico

Cree correos electrónicos personalizados y relevantes para el contexto que sean coherentes con el resto de la experiencia del cliente.

![](assets/new-email-content.png)


En el siguiente ejemplo, se muestran los pasos para diseñar una entrega de correo electrónico en Adobe Campaign que contenga datos personalizados, vínculos a una dirección URL externa y un vínculo a la página espejo.

1. **Creación de la entrega**

   Para crear un nuevo envío, vaya a **Campañas** pestaña, haga clic en **Envíos** y haga clic en **Crear** botón situado sobre la lista de envíos existentes.

   ![](assets/delivery_step_1.png)

1. **Seleccione la plantilla**

   Seleccione una plantilla de envío y asigne un nombre a la entrega. Este nombre solo está visible para los usuarios de la consola de Adobe Campaign y no para los destinatarios. Sin embargo, este título se muestra en la lista de envíos. Haga clic en **[!UICONTROL Continue]**.

   ![](assets/dce_delivery_model.png)

1. **Importar el contenido**

   Haga clic en **Origen** para pegar el contenido del HTML.

   ![](assets/paste-content.png)


1. **Personalice su mensaje**

   * Adición del nombre y los apellidos de los destinatarios

     Para insertar el nombre y los apellidos de los perfiles de destino en el contenido del mensaje, coloque el cursor donde desee insertarlos y haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL Greetings]**.

     ![](assets/include-greetings.png)

     Vaya a la pestaña preview para comprobar la personalización seleccionando un destinatario.

     ![](assets/perso-check.png)

     Obtenga más información sobre las opciones de personalización en [esta sección](personalize.md).

   * Inserción de un vínculo rastreado

     Para transferir los destinatarios de envíos a una dirección externa a través de una imagen o un texto, selecciónelo y haga clic en **[!UICONTROL Add a link]** en la barra de herramientas.

     Introduzca la dirección URL del vínculo en el campo **URL** con el formato **https://www.myURL.com** y, a continuación, confirme la acción.

     ![](assets/add-a-link.png)

   * Adición de una página espejo

     Para permitir que los destinatarios vean el contenido de su envío en un explorador web, agregue un vínculo a la variable [página espejo](mirror-page.md) del mensaje.

     Coloque el cursor donde desee insertar este vínculo, haga clic en el último icono de la barra de herramientas y, a continuación, haga clic en **[!UICONTROL Include]** y seleccione **[!UICONTROL link to mirror page]**.

     Obtenga más información acerca de la administración de la página espejo en [esta sección](mirror-page.md#link-to-mirror-page).

1. Puede definir parámetros adicionales para el correo electrónico, como enviar una copia de los mensajes a una dirección de la BBC, cambiar el formato del mensaje, configurar una codificación específica, etc. Obtenga más información en [esta sección](email-parameters.md).

1. Cuando el contenido esté listo, haga clic en **Guardar**: ahora se muestra en la lista de envíos, en la **[!UICONTROL Campaigns > Deliveries]** pestaña.

Su primer envío de correo electrónico está listo. Ahora debe definir la audiencia, validar la entrega y enviarlo.

Obtenga información sobre cómo importar un contenido de correo electrónico en esta [caso de uso](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html).

Obtenga más información en las siguientes secciones:

<!--[Design an email in Campaign]-->
* [Creación y uso de una plantilla de correo electrónico](../send/create-templates.md)
* [Seleccione la audiencia del correo electrónico](../audiences/gs-audiences.md)
* [Validación de una entrega y envío de pruebas](preview-and-proof.md)
* [Configuración y envío de la entrega](configure-and-send.md)

## Prueba y validación de correos electrónicos

Campaign ofrece varias formas de probar y validar los correos electrónicos antes de enviarlos a sus audiencias. Obtenga información sobre cómo previsualizar y probar el contenido de correo electrónico en [esta sección](../send/preview-and-proof.md).

Puede hacer lo siguiente:

* [Envío de pruebas](preview-and-proof.md)
* [Adición de direcciones semilla](../audiences/test-profiles.md)
* [Comprobación de registros de análisis de envío](delivery-analysis.md)

